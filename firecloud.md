Using the Broad FireCloud
------------------------------
Eric T Dawson  
Updated: March 2019

## Dockerizing a tool
See the docker.md tutorial for additional information on dockerizing a tool

## Writing a WDL description

## Notes about imports
There are some important rules about imports:  
1. Imported WDLs must be in FireCloud (GitHub imports are vaporware).
2. Imported WDLs must be publicly readable, and
3. Default WDL permissions are not publicly available, and
4. WDL permissions reset on push, so you need to update them every
time there's a fresh snapshot.
5. WDLs can only be registed on FireCloud if they are a workflow, but
you can use an empty dummy workflow without issue.

## Pushing to FireCloud
The FireCloud CLI has been deprecated and no longer works, however FISS
(FireCloud Selector Service) is functional if undocumented.

To push a tool to FireCloud using FISS, the command is:
```
fissfc meth_new
```
This both adds new tools and updates existing tools. The full usage is:  
```
fissfc meth_new -d <WDL file> -n <namespace> -m <tool name in FireCloud>
```

## Making tasks and workflows public
1. Navigate to the Method Repository
2. Find and naviagate to the tool page.
3. Click "Permissions"
4. Tick the "Publicly Readable" box.

## Editing your configuration in FireCloud
From the tool's method repository page:
1. Select "Export to Workspace"
2. If no configuration is available, select "Use Blank Configuration"
3. Select you workspace, the entity type, and hit "Export"


In your workspace:
1. Go to the Method Configurations tab and locate your tool.
2. Click "Edit"
3. Update the Snapshot if necessary
4. Fill in the requisite inputs
    - "workspace.*" for workspace-level inputs
    - "this.*" for entity (sample/pair/set/etc) level inputs
    - "this.sample_id" and "this.pair_id" are always available even if you can't see them.

## Running your workflows