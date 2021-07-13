# Xend Payment SDK

This is the live Xend Payment Sdk. Like the live one, it allows a user to make payments via the payment methods made available to them by xend. For now, the sdk supports making payments
via 
* Xend (If the sender is already a xend user)
* Bank account (If the sender or the sendee have reserved an account for this purpose)
* Paystack 
* Monnify

### How to Use
You can use jsdeliver to allow github to serve they sdk in your project 

### Inline sample
```html
<form >
    <script src="https://cdn.jsdelivr.net/gh/xend-services/sdkassets/payxend.min.js"></script>
    <button type="button" onclick="openXendSdk()"> Pay </button> 
</form> 
```
### Demo

You can take a look at what this looks like here [demo](https://ada-h.github.io/demo)

``` javascript
<script>
    function openXendSdk(){
    
        Payment.setup(
            {
                amount: 0,
                customerName: '',
                receiverName: '',
                image: '',
                referenceToken: '',
                customerEmail: '',
                paymentPurpose: '',
                customerNumber: '',
                invoiceNum: '',
                receiverXendCode: '',
                customerXendCode: '',   
                onXendComplete: function(response){
                    // Implement what should happen when the function has been completed
                    console.log(response)
                },
                onclose: function(){
                    //Implement what should happen when the modal is closed here
                   alert('window closed')
                }  
            }
        )
    } 

    
</script> 
```

### Requirements
 * {Number} amount - Amount user wants to pay in kobo.
 * {String} customerName -  Customer's name.
 * {String} receiverName -  Receiver's name.
 * {String} image - Receiver's image.
 * {String} referenceToken - refrence token for when paying for subscription
 * {String} customerEmail - Customer's email.
 * {String} paymentPurpose - Purpose can be 'Subscription' or 'MerchantBranch' or MerchantCustomer' or 'Invoice'.
 * {String} customerNumber - Customer's phone number
 * {String} invoiceNum  - Customer's invoice number if payment is via invoice, otherwise, return empty string
 * {String} receiverXendCode - Receiver's Xend Code
 * {String} customerXendCode - Customer's Xend Code
 * {Function} onXendComplete - A function that allows you to perform an action when the transaction is closed
 * {Function} onclose - A function that is called when the payment sdk is closed before the transaction is completed
