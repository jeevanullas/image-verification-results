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



