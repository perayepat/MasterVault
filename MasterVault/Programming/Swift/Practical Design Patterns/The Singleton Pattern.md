# Purpose, pros and cons
![[Pasted image 20220518105335.png]]

![[Pasted image 20220518105515.png]]
![[Pasted image 20220518105551.png]]
![[Pasted image 20220518105647.png]]

# Read-Only singletons
A class called app setting is created 

Sharing data across the whole app is now thread safe *(Meaning when mutltple threads are accessing the singlton data no duplicates will be created)*

``` Swift 
final public class AppSettings{

	//We access the only instance by a appSetting property
	
	public static let shared = AppSetting()

	private var settings: [String: Any] = ["Theme" : "Dark", 
    "MaxConsurrentDownload" : 4]

	// Prevent clients from accesseing it directly we use this 
	
	private init(){}
	
		// These methods will access the settings dictionary 
		//1st Return a string for a given key and 2nd return a int 
		
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

//Printing it wil give you 4
```

# Concurrency Issues

