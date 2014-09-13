# Deployment Plan
-------
### Merge Dev Branch into Master
* $ git checkout master
  * Switches to the local master branch
* $ git pull **github** master
  * Resolve any conflicts
   * $ git add -A
   * $ git commit -am ‘Relevant detailed commit message.’
   * $ git pull github master
  * $ git merge **newFeatureName**
   * Resolve any conflicts

### Test 
* Check that all issues are resolved
* $ git push github master

### Tag Your Release
* $ git tag -a v**X.X.X** -m ‘**Release Code or Feature Name** ’
  * **Example:** Release Version (dot) Production Release ++ (dot) Staged Release ++
   * Staged Release: v0.1.13 turns into v0.1.14
   * Production Release: v0.1.14 turns into v0.2.0

* $ git push github --tags

### Communicate with team
* Announce change to staging server
* Verify the testing of the last feature to be promoted has completed.

### Promote to Staging
* $ git push staging master

### Test Staging
* Replicate any issues in local dev environment
* A new local dev branch may be needed to start over

### Promote to Production
* Have other users try it out prior to going live in production
* If no issues are present promote to Production server