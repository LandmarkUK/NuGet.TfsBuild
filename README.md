NuGet.TfsBuild
==============

NuGet.TfsBuild allows the TFS Build service to perform package-restore from a private, password protected repository.
As a bonus, in v1.1 you can configure NuGet to use a proxy if required.

It works by injecting a new package source into the NuGet.config file installed when you enable package-restore, with settings defined by MSBuild parameters.

## Getting Started 

- Enable NuGet Package Restore for your solution.
- Install NuGet.TfsBuild into your main solution (e.g. Your web app / deployable)
-- You can work out which one by running MSBuild from the command line for your solution and seeing what the topmost project built is.
- Set up a TfsBuildService build definition
- In the Advanced section of the Build Process tab, add the following (substituting values as appropriate)

```
/p:PrivateNuGetRepository={path to my private repo feed}
/p:PrivateNuGetRepositoryUsername={my build user username}
/p:PrivateNuGetRepositoryPassword{my build user password}
/p:NuGetHttpProxy=http://{myproxyurl}:{port}
/p:NuGetHttpProxyUser={myProxyUser}
```

- Build under Tfs Build service and enjoy seeing package restore pull your packages from your secure private package repository.

## Get Involved

Fork it... Fix it... Raise Issues... Generate Pull requests... Use it!

## Thanks

Thanks have to go to my company, Landmark Information Group ( http://www.landmark.co.uk / http://twitter.com/LandmarkUK ) 
for allowing this project to be open sourced under the Apache 2.0 license.
