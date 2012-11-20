image-verification-results
==========================

Repository for test results of images hosted on emis.eucalyptus.com.

The images should be listed here:

https://github.com/eucalyptus/eucalyptus/wiki/Starter-Images

## Testing

After image has been added to the Starter-Images wiki, use eutester to test the instance.  The instancetest.py testcase under cloud_user should be used.  The "BasicInstanceChecks", "MetaData", and "Reboot" tests are the minimal tests to run to validate an image.  Here is an example of how to run the tests:

<code>
./testcases/cloud_user/instances/instancetest.py  --emi emi-847837A3 --credpath ../creds/ --tests BasicInstanceChecks MetaData Reboot
</code>

After running the tests, add the results to image-verification-results repo on github.  Here is an example:

* This is for the CentOS 6.3 x86_64 image *

<code>
git clone https://github.com/eucalyptus/image-verification-results.git</code>

<code>cd image-verification-results</code>

<code>### add output of instancetest.py to textfile ###</code>

<code>git add .</code>

<code>git commit -m "Eutester Test Case for CentOS 6.3 Image x86_64"</code>

<code>git push origin master</code>

After pushing the results file, update the "Latest test" column on the Starter-Images page by referencing the URL to the file in the image-verification-results repo.




