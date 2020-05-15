# Make a Phone Call

To open the phone app and dial a phone number, use the ACTION_DIAL action and specify a phone number using the URI scheme defined below. When the phone app opens, it displays the phone number but the user must press the Call button to begin the phone call.

```kotlin
fun dialPhoneNumber(phoneNumber: String) {
    val intent = Intent(Intent.ACTION_DIAL).apply {
        data = Uri.parse("tel:$phoneNumber")
    }
    if (intent.resolveActivity(packageManager) != null) {
        startActivity(intent)
    }
}
```
[source](https://developer.android.com/guide/components/intents-common#Phone)
