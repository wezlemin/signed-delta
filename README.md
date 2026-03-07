# signed-delta
Example (this uses the China National Heavy Duty Truck Group Co., Ltd certificate): <br>
itms-services://?action=download-manifest&url=https://raw.githubusercontent.com/wezlemin/signed-delta/refs/heads/main/Truck.plist

---

## How to create a Direct Install for Delta

### 1. Download the IPA

* Follow the tutorial here: [Delta IPA Sign Tutorial](https://rentry.co/delta-ipasignx).
* **Important:** Instead of clicking **Install Now**, choose **Download IPA**.

### 2. Host the IPA

* Upload the IPA file to a hosting service (e.g., GitHub, Dropbox, or any static file host).
* Make sure the file is publicly accessible.

### 3. Prepare the Plist

* Upload a `.plist` file (e.g., `Truck.plist`) to a public URL.
* Open the plist in a text editor and replace the `<string>` URL with your IPA's hosted URL:

```xml
<string>YOUR_UPLOADED_IPA_URL.ipa</string>
```

### 4. Install via itms-services

* On your iOS device, open Safari and go to:

```
itms-services://?action=download-manifest&url=PLIST_URL
```

* Tap **Open**, then **Install**.

### 5. Trust the App

* Go to **Settings → General → VPN & Device Management** (or Profiles & Device Management).
* Find your app’s profile and tap **Trust**.

### ✅ Done

* The Delta app should now appear on your home screen and be ready to use. You can share the itms-services:// with others, and it should work for them too (unless they are blacklisted or revoked from the certificate).
