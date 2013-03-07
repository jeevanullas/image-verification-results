image-verification-results
==========================

Repository for test results of images hosted on emis.eucalyptus.com and eustore.

The images should be listed here:

https://github.com/eucalyptus/eucalyptus/wiki/Starter-Images

Please input all the information under each column.  

## Testing and Contributing

After image has been added to the Starter-Images wiki, use eutester to test the instance.  The instancetest.py testcase under cloud_user should be used.  The "BasicInstanceChecks", "MetaData", and "Reboot" tests are the minimal tests to run to validate an image.  Here is an example of how to run the tests:

<pre>
./testcases/cloud_user/instances/instancetest.py  --emi emi-847837A3 --credpath ../creds/ 
--tests BasicInstanceChecks MetaData Reboot
</pre>

After running the tests, add the results to image-verification-results repo on github.  Here is an example:

* This is for the CentOS 6.3 x86_64 image *

1.  Do a fork of Eucalyptus image-verification-results project (requires github account for information on how to set up a Github account, refer to the following URL: [http://help.github.com/set-up-git-redirect/](http://help.github.com/set-up-git-redirect/)).  On information on how to fork a project, refer to the following link: [http://help.github.com/fork-a-repo/](http://help.github.com/fork-a-repo/).

2.  Clone image-verification-results project from user's github account (for example =>  [hspencer77/image-verification-results](https://github.com/hspencer77/image-verification-results)):

  <code>git clone https://github.com/hspencer77/image-verification-results.git</code>

3. Add the eucalyptus/image-verification-results as a upstream remote:

  <code>cd image-verification-results</code>
  
  <code>git remote add upstream https://github.com/eucalyptus/image-verification-results.git</code>
  
  <code>git fetch upstream</code>

4. After doing that, put the results of the eustester testcase for the image into a text file:

  <code>### add output of instancetest.py to textfile ### (for example, we created one called centos6.3-eutester-testresults.txt</code>

5. Once the text file is created, add it to the local repo, and put in the appropriate commit message:
  
  <code>git add .</code>
  
  <code>git commit -m "Eutester Test Case for CentOS 6.3 Image x86_64"</code>

6. Finally, push the code to master to prepare for a pull request:
  
  <code>git push origin master</code>

7. Once the test results have been pushed to master, do a pull request to the eucalyptus/image-verification-results project.  For information on how to do a pull request in Github, refer to the following help link: [http://help.github.com/send-pull-requests/](http://help.github.com/send-pull-requests/).

After the pull request has been merged, we will do the following:

  * update the "Latest Test" column on the Starter-Images page by referencing the URL to the file in the image-verification-results repo.
  * update the URL under "URL to Image" to reference the location on emis.eucalyptus.com.
  * update the catalog file on emis.eucalyptus.com so that eustore can access the new image.

For any questions concerning how to use Euster, please refer to https://github.com/eucalyptus/eutester.



