# MCAWSS3Client


[Amazon S3](http://aws.amazon.com/s3/) client based on [AFNetworking](https://github.com/AFNetworking/AFNetworking)'s [AFHTTPClient](http://afnetworking.github.com/AFNetworking/Classes/AFHTTPClient.html).

## Example Usage

```objc
MCAWSS3Client* client = [[MCAWSS3Client alloc] init];
[client setAccessKey:@"..."];
[client setSecretKey:@"..."];
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



## License

MCAWSS3Client is © 2012 [Mirego, Inc.](http://www.mirego.com) and may be freely distributed under the [New BSD license](http://opensource.org/licenses/BSD-3-Clause). See the `LICENSE` file.