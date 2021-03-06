# inventor-thumbnail

Sample scripts for creating and running a Forge Design Automation
pipeline that generates a thumbnail from an Autodesk Inventor file.

The _setup-pipeline_ script:
- creates (or updates) an app bundle for Autodesk Inventor engine,
  using a pre-packaged Inventor plugin _ThumbnailPlugin.bundle.zip_
- creates (or updates) an alias pointing to the latest version of the app bundle
- creates (or updates) an activity with the Inventor plugin that
  takes an Inventor file as its input, and generates an image file
  on its output
- creates (or updates) an alias pointing to the latest version of the activity

The _run-pipeline_ script:
- uploads an example Inventor file included with this sample
- creates signed URLs for the input Inventor file and the output thumbnail
- creates a work item for the activity defined during the setup
- waits for the work item to complete
- downloads the thumbnail image to _output_ subfolder

## Running

### On macOS/linux

#### Bash script

```bash
export FORGE_CLIENT_ID=<your client id>
export FORGE_CLIENT_SECRET=<your client secret>
export FORGE_BUCKET=<your bucket>
./setup-pipeline.sh
./run-pipeline.sh
```

#### Node.js script

```bash
export FORGE_CLIENT_ID=<your client id>
export FORGE_CLIENT_SECRET=<your client secret>
export FORGE_BUCKET=<your bucket>
node setup-pipeline.js
node run-pipeline.js
```

### On Windows

#### PowerShell script

```powershell
$env:FORGE_CLIENT_ID = "<your client id>"
$env:FORGE_CLIENT_SECRET = "<your client secret>"
$env:FORGE_BUCKET = "<your bucket>"
.\setup-pipeline.ps1
.\run-pipeline.ps1
```

#### Node.js script

```powershell
$env:FORGE_CLIENT_ID = "<your client id>"
$env:FORGE_CLIENT_SECRET = "<your client secret>"
$env:FORGE_BUCKET = "<your bucket>"
node setup-pipeline.js
node run-pipeline.js
```
