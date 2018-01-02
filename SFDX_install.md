Installing with SFDX

 Starting in the root of one of the sfdx projects (either the screen component one or the actions component one, and not the same as the root of the github parent project):
  if you want to push to a scratch org, run sfdx force:source:push
  if you want to deploy to a regular org:
    1. create a metadata version of the project:
           a. make a tempdir to hold the metadata:
                     mkdir mdapioutput
           b. convert the source to metadata
                     sfdx force:source:convert -d mdapioutput/
      2. deploy to your org:
           sfdx force:mdapi:deploy -d mdapioutput/ -u MyOrgAlias -w 100
  Note: if you only want to try deploying a subset of the components, create a package.xml specifying the specific ones to use.
  Note: for great tutorials on all of this, see (https://trailhead.salesforce.com/trails/sfdx_get_started)