# Overview 
This pattern is used when your adapting an old method or api to your new application this acts as a buffer to connect the old and new.
![[Pasted image 20220608144440.png]]
![[Pasted image 20220608144520.png]]


# Code 
``` Swift
protocol PaymentGateway {
    func receivePayment(amount: Double)
    var totalPayments: Double {get}
}

    /// The classes adopt the payment protocol
    ///
class PayPal: PaymentGateway {
    private var total = 0.0
    
        /// Adds the to the private total valie
    func receivePayment(amount: Double) {
        total += amount
    }
    
        ///Outputs the accumulated total
    var totalPayments: Double {
        print("Total payments received via PayPal: \(total)")
        return total
    }
}

class Stripe: PaymentGateway {
    private var total = 0.0
    
    func receivePayment(amount: Double) {
        total += amount
    }
    
    var totalPayments: Double {
        print("Total payments received via Stripe: \(total)")
        return total
    }
}

    // The structs in use
let paypal = PayPal()
paypal.receivePayment(amount: 100)
paypal.receivePayment(amount: 200)
paypal.receivePayment(amount: 499)

let stripe = Stripe()
stripe.receivePayment(amount: 5.99)
stripe.receivePayment(amount: 25)
stripe.receivePayment(amount: 9.99)

    /// To calculate total payments through all the gate ways
    /// This list is for that
var paymentGateways: [PaymentGateway] = [paypal, stripe]





    // third-party class, that doesn't conform to PaymentGateway
class AmazonPayments {
    var payments = 0.0
    
    func paid(value: Double, currency: String) {
        payments += value
        print("Paid \(currency)\(value) via Amazon Payments")
    }
    
    func fulfilledTransactions() -> Double {
        return payments
    }
}


let amazonPayments = AmazonPayments()
amazonPayments.paid(value: 120, currency: "USD")
amazonPayments.paid(value: 74.99, currency: "USD")


    //MARK: Adapting the amazon payment
class AmazonPaymentsAdapter: PaymentGateway{
    
    func receivePayment(amount: Double) {
        amazonPayments.paid(value: amount, currency: "USD")
    }
    
        // retuns the valie of amaazon payments
    var totalPayments: Double{
        let total = amazonPayments.payments
        print("Amazon Payments: \(total)")
        return total
    }
}


    //Using the adapter
let amazonPaymentsAdapter  = AmazonPaymentsAdapter()
amazonPaymentsAdapter.receivePayment(amount: 390)
amazonPaymentsAdapter.receivePayment(amount: 20)


paymentGateways.append(amazonPaymentsAdapter)


    //Total calculated in the for in loop
    //Relies on polymorphism
var total = 0.0
for gateway in paymentGateways {
    total += gateway.totalPayments
}

print(total)

```

# Code using type extensions
Easier way of implemnting the adapter 
``` Swift 
    //MARK: Using extenstions
extension AmazonPayments : PaymentGateway{
    
    func receivePayment(amount: Double) {
        amazonPayments.paid(value: amount, currency: "USD")
    }
    
        // retuns the valie of amaazon payments
    var totalPayments: Double{
        let total = amazonPayments.payments
        print("Amazon Payments: \(total)")
        return total
    }
}



    //Using the adapter
let amazonPayments  = AmazonPayments()
amazonPayments.receivePayment(amount: 390)
amazonPayments.receivePayment(amount: 20)


paymentGateways.append(amazonPayments)

```