# Purpose, pros and cons
![[Pasted image 20220518105335.png]]

![[Pasted image 20220518105515.png]]
![[Pasted image 20220518105551.png]]
![[Pasted image 20220518105647.png]]

# Read-Only singletons
A class called app setting is created 


Sharing data across the whole app is now thread-safe *(Meaning when multiple threads are accessing the singleton data no duplicates will be created)*

``` Swift 
final public class AppSettings{

	//We access the only instance by an app setting property
	
	public static let shared = AppSetting()

	private var settings: [String: Any] = ["Theme" : "Dark", 
    "MaxConsurrentDownload" : 4]

	// Prevent clients from accessing it directly we use this 
	
	private init(){}
	
		// These methods will access the settings dictionary 
		//1st Return a string for a given key and 2nd return an int 
		
	public func string(forKey key: String) -> String? {
			return settings[key] as? String
		}

	public func int(forKey key: String) -> Int? {
			return settings[key] as? Int
		}
	
}
```


**Accessing it in another class**

``` SWift 
let maxConcurrentDownloads = AppSettings.shared.int(forKey:"MaxConsurrentDownload" )

//Printing it will give you 4
```

# Concurrency Issues
**Problem**
You have to read and write to your singleton at the same time. 


**Solution**
This will make the singleton thread safe and optimise it for writing and reading in parallel. 
reading and writing to a single singleton without the `concurrentQueue` will corrupt the data in your singleton and crash the app 

After this change, the methods can be accessed in parallel, read happens in ordinary blocks and write happens in barrier blocks. 

![[Pasted image 20220523102818.png]]

``` Swift
	final public class AppSettings {

		public static let shared = AppSetting()

		private var settings: [String: Any] = ["Theme" : "Dark", 
	    "MaxConsurrentDownload" : 4]
	    
	
		private let concurrentQueue = DisapatchQueue( 
	    label: "concurrentQueue", attributes: 
	    .concurrent)
	
		private init(){}

		public func string(forKey key: String) -> 
	         String? {
	         var result: String?
	         concurrentQueue.sync{
				result =  settings[key] as? String
				}
				return result
			}

		public func int(forKey key: String) -> Int? {
		
				 var result: Int?
	         concurrentQueue.sync{
				result =  settings[key] as? Int
				}
				return result
			}



		public func set(value: Any, forkey key: String){
			concurrentQueue.async(flags: .barrier){
			self.setting[key] = value
			}
		}
	
	}
```

**This is how you'd set values when its thread safe**
``` Swift 
    let callCount  = 100

     for callIndex in 1...callCount{

            //we use the `concurrentQueue.async` to set values to the Singleton

            concurrentQueue.async {

               AppSettings.shared.set(value: callIndex , forkey:String(callIndex))

           }

       }
```


