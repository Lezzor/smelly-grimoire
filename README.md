# smelly-grimoire
Publicly available notes for anyone who is curious


## Download apps from app store
Google IPATool github

However, you will need to have homebrew installed on your mac (the homebrew command is on the github page)

Once setup, you should see it via running `ipatool`

Log into ipa tool using:
`ipatool auth login -e <apple_id_email>`
Then enter your apple id pass

Find app using ipatool:
`ipatool search <keyword>`

Using results from the previous tool you can download the app:
`ipatool download --bundle-identifier <BundleID e.g. com.apple.TestFlight>`

## Set up objection iOS

Create a Xcode project:
Get hello world application. 
Make sure physical iPhone is plugged in
Click on the device name in xcode (should be close to the top of the nav bar) and then hit run in Xcode and it will install the app into your physical iPhone

To allow the app to run on iPhone. Navigate to the iPhone settings
Settings > general > profiles and device management > Trust "Apple Development..."

Now in the terminal run `security find-identity`
Under Policy: X.509 Basic in the numbered list, you should see a long string in hex. You can use these developer profiles for patching our app

pip3 install frida-tools
pip3 install objection
objection patchipa --source <ipa_file>  -c <developer_profile>

Once the objection app is installed you can open it up on your host using:
`objection explore`
