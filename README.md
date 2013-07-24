# MCAWSS3Client - Amazon S3 client based on AFHTTPClient.

[Amazon S3](http://aws.amazon.com/s3/) client based on [AFNetworking](https://github.com/AFNetworking/AFNetworking)'s [AFHTTPClient](http://afnetworking.github.com/AFNetworking/Classes/AFHTTPClient.html).

## Example Usage

```objc
MCAWSS3Client* client = [[MCAWSS3Client alloc] init];
[client setAccessKey:@"..."];
[client setSecretKey:@"..."];
[client setSessionToken:@"..."]; // optional session token (necessary when using AWS STS credentials)
[client setBucket:@"the-bucket"];

[client putObjectWithData:imageData
                      key:key
                 mimeType:@"image/jpg"
               permission:MCAWSS3ObjectPermissionsPrivate
                  success:^(AFHTTPRequestOperation *operation, id responseObject) {
                      NSLog(@"Upload Successful!");
                  } failure:^(AFHTTPRequestOperation *operation, NSError *error) {
                      NSLog(@"Upload Failed...");
                  }];
```


## Important Notes

- This code has been known to work on iOS 5.x+.
- This code uses **Automatic Reference Counting**, if your project does not use ARC, you must add the `-fobjc-arc` compiler flag to each implementation files in `Target Settings > Build Phases > Compile Source`.
- This code also uses the **literals syntax**, so at least Xcode 4.5 is required.


## Adding to your project

If you're using [`CocoaPods`](http://cocoapods.org/), there's nothing simpler.
Add the following to your [`Podfile`](http://docs.cocoapods.org/podfile.html)
and run `pod install`

```
pod 'MCAWSS3Client', :git => 'https://github.com/mirego/MCAWSS3Client.git'
```

Don't forget to `#import "MCAWSS3Client.h"` where it's needed.

## License

MCAWSS3Client is © 2013 [Mirego](http://www.mirego.com) and may be freely
distributed under the [New BSD license](http://opensource.org/licenses/BSD-3-Clause).
See the [`LICENSE.md`](https://github.com/mirego/MCAWSS3Client/blob/master/LICENSE.md) file.

## About Mirego

Mirego is a team of passionate people who believe that work is a place where you can innovate and have fun. We proudly build mobile applications for [iPhone](http://mirego.com/en/iphone-app-development/ "iPhone application development"), [iPad](http://mirego.com/en/ipad-app-development/ "iPad application development"), [Android](http://mirego.com/en/android-app-development/ "Android application development"), [Blackberry](http://mirego.com/en/blackberry-app-development/ "Blackberry application development"), [Windows Phone](http://mirego.com/en/windows-phone-app-development/ "Windows Phone application development") and [Windows 8](http://mirego.com/en/windows-8-app-development/ "Windows 8 application development") in beautiful Quebec City.

We also love [open-source software](http://open.mirego.com/) and we try to extract as much code as possible from our projects to give back to the community.
