# Testing Checklist

This is the official checklist template for upgrading UseGalaxy.no to new releases. 
When an upgrade is to be performed, create a new issue in the issue tracker and copy/paste the relevant tests from this list into that issue (in raw markdown code).

### After upgrade
- [ ] Login to the server and run `sudo systemctl status` to check that all the services are up and running correctly under "system.slice" (not under "user.slice")
- [ ] Login to the server and run `ps -eo pid,user,cmd` to check that the services are owned by the correct OS user ("galaxy")
- [ ] Use this API call in a web brower to check that you now have the correct and expected Galaxy version https://usegalaxy.no/api/version 

### Style and authentication
- [ ] Check that the NeLS styling is correct, including masthead logo and colors
- [ ] Check that our custom login page has the correct style and contents
- [ ] Check that login works with FEIDE
- [ ] Check that login works with NeLS IdP
- [ ] Check that logout works correctly and that you have to re-enter your password to log in again

### Links and masthead buttons
- [ ] Check that the Help menu includes a link to "Support" and that this link takes you to the help desk web page at https://elixir.no/helpdesk
- [ ] Check that the Help menu includes a link to "Terms & conditions" and that this link brings up our terms of service document
- [ ] Galaxy release notes webhook (bullhorn icon)
- [ ] Training materials webhook (graduation cap icon)
- [ ] Backend status webhook (heartbeat icon)
- [ ] Update log webhook (calendar icon)

### Data Import/export
- [ ] Import a file from your local computer into your history via the Upload Data button
- [ ] Check that these uploads are handled by TusD
- [ ] Import a file directly from the tool form
- [ ] Import a file by dragging it into Galaxy from an external OS file browser on your computer
- [ ] Download a single file from your history (download button)
- [ ] Download a collection from your history as a zip-file  (click on the collection and then press download button). Extract and inspect the files in the zip-archive afterwards
- [ ] Deferred dataset resolution (Choose "paste/fetch data" in the Upload dialog and paste in a dataset URL, then press the "Settings" cogwheel button and check off "Defer dataset resolution")
- [ ] **NeLS Storage** 
  - [ ] Import a single file from the NeLS Storage (and display it!)
  - [ ] Import multiple files from the NeLS Storage in a single operation (and display them!)
  - [ ] Export one or more files to the NeLS Storage
  - [ ] Export one or more files to the NeLS Storage into a new directory
  - [ ] Export a history from Galaxy to NeLS Storage
  - [ ] Import a history from NeLS Storage to Galaxy
- [ ] **Remote storage sources**
  - [ ] Import a file from an FTP server
  - [ ] Import a file from a custom SSH server
  - [ ] Export a file to a custom SSH server
- [ ] **Histories**
  - [ ] Import a history from a file (in tgz and/or ROC-format)
  - [ ] Export a history to a file (in tgz and/or ROC-format)
  - [ ] Import a history from another Galaxy server via link
  - [ ] Export a history to another Galaxy server via link
  - [ ] Archive a history in NeLS Storage and free up the disk
  - [ ] Import an archived history back into Galaxy

### Tools
- [ ] Run a tool that comes bundled with Galaxy (e.g. "select first" or "add column")
- [ ] Run a tool that was installed from a tool shed
- [ ] Run a tool that uses the default container (it does not have "requirements" in the wrapper)
- [ ] Run a tool that uses a CVMFS reference dataset from "data.galaxyproject.org" (e.g. Bowtie2)
- [ ] Run a tool that uses a CVMFS reference dataset from "data.usegalaxy.no" (e.g. RNA STAR with built-in gene model "hg38 with Ensembl annotations")
- [ ] Run a tool that uses a local reference dataset (e.g. Salmon Quant with built-in index "Transcriptome of Sea Louse from ENSEMBL release 56 with decoys")
- [ ] Run a tool that writes temp-files to "/tmp" (e.g. FastQC)
- [ ] Switch Tool Panel mode to sort tools by EDAM operations or topics
- [ ] Search for tools with the advanced tool search

### Workflows
- [ ] Run a workflow (that generates a report)
- [ ] Run a workflow with conditional workflow steps ([example](https://folk.ntnu.no/kjetikl/galaxy/Galaxy-Workflow-test_conditional_23.ga)) 
- [ ] **Workflow invocations**
  - [ ] Inspect the workflow invocation details afterward running a workflow
  - [ ] Look at the workflow invocation report
  - [ ] Export a workflow invocation as RO-crate
- [ ] **Workflow editor** 
  - [ ] Add comments and drawings
  - [ ] Use mouse wheel to change zoom level in workflow editor
- [ ] Import a workflow GA4GH TRS servers

### Histories
- [ ] Show histories side by side in "multi-view" mode
- [ ] Drag’n’ drop datasets between histories in the "history multi-view" 
- [ ] **Bulk history operations**
  - [ ] Add tags to multiple selected datasets 
  - [ ] Add tags to a dataset collection 
  - [ ] Remove tags from multiple selected datasets
  - [ ] Remove tags from a dataset collection
  - [ ] Change genome build for multiple selected datasets
  - [ ] Change genome build for a dataset collection
  - [ ] Change data type for multiple selected datasets
  - [ ] Change data type for a dataset collection

### Miscellaneous
- [ ] Test a Visualization plugin (if configured), e.g. "Charts"
- [ ] Test a Display Application (if configured), e.g. "UCSC Genome Browser"
- [ ] Test the scratchbook function by clicking the 3x3 grid icon in the top menu and then press the "display" (eye) button on multiple datasets
- [ ] Send a Bug report by clicking the bug button on a failed job
- [ ] Send a notification to users (personal and/or broadcast)

