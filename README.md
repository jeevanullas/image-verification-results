image-verification-results
==========================

Repository for test results of images hosted on emis.eucalyptus.com and eustore.

The images should be listed here:

https://github.com/eucalyptus/eucalyptus/wiki/Starter-Images

## Testing

After image has been added to the Starter-Images wiki, use eutester to test the instance.  The instancetest.py testcase under cloud_user should be used.  The "BasicInstanceChecks", "MetaData", and "Reboot" tests are the minimal tests to run to validate an image.  Here is an example of how to run the tests:

```
./testcases/cloud_user/instances/instancetest.py  --emi emi-847837A3 --credpath ../creds/ 
--tests BasicInstanceChecks MetaData Reboot --instance-user root
```

After running the tests, add the results to image-verification-results repo on github.  Here is an example:

* This is for the CentOS 6.3 x86_64 image *

```
git clone https://github.com/eucalyptus/image-verification-results.git

cd image-verification-results

### add output of instancetest.py to textfile ###

git add .

git commit -m "Eutester Test Case for CentOS 6.3 Image x86_64"

git push origin master
```

After pushing the results file, update the "Latest test" column on the Starter-Images page by referencing the URL to the file in the image-verification-results repo.

For any questions concerning how to use Euster, please refer to https://github.com/eucalyptus/eutester.



