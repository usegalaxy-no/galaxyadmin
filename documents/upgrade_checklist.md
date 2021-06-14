# Testing Checklist

This is the official checklist template for upgrading UseGalaxy.no to new releases. 
When an upgrade is to be performed, create a new issue in the issue tracker and copy/paste the relevant tests from this list into that issue (in raw markdown code).

### Updates to custom modified Galaxy files

- [ ] The following three Galaxy code files (plus one style file) are replaced with our own custom modified copies in the playbooks. We must check if any of these have been updated since the previous Galaxy release, and if so, we should merge the new changes into our own copies.

* client/src/mvc/history/options-menu.js
* client/src/components/login/Login.vue
* lib/galaxy/authnz/psa_authnz.py
* client/src/style/scss/theme/blue.scss

### Looks and auth
- [ ] Use the API to check that you now have the correct and expected version  https://(test.)usegalaxy.no/api/version
- [ ] Check that the styling is correct and looks like this example (example to be updated?)
- [ ] Check that login works with FEIDE
- [ ] Check that login works with NeLS IdP
- [ ] Check that logout works correctly and that you have to re-enter your password to log in again.

### Links 
- [ ] Check that the Help menu includes a link to "Support" and that this link takes you to the help desk web page at https://elixir.no/helpdesk
- [ ] Check that the Help menu includes a link to "Terms & conditions" and that this link brings up the terms of service document in the middle panel
- [ ] ~~Check that the “Galaxy Support” link in the Help menu takes you to https://galaxyproject.org/support~~

### Basic operations
- [ ] Import a file from your local computer into your history
- [ ] Import a single file from the NeLS Storage (and display it!) 
- [ ] Import multiple files from the NeLS Storage in a single operation (and display them!)
- [ ] Export one or more files to the NeLS Storage
- [ ] Test a history export from Galaxy to NeLS
- [ ] Test a history import from NeLS to Galaxy
- [ ] Run a tool that comes bundled with Galaxy (e.g. "replace text")
- [ ] Run a tool that was installed from a tool shed
- [ ] Run a tool that uses a reference dataset (e.g. bwa-mem)
- [ ] Test a workflow
- [ ] Test a Visualization plugin (if configured), e.g. “Charts” (example of a tool that typically would produce outputs ready for Charts to visualize?)
- [ ] Test Trackster visualization
- [ ] Test a Display Application (if configured), e.g. “UCSC Genome Browser”

### New stuff v20.01
- [ ] workflow documentation. When it has finished, select “Workflow Invocations” from the “User” menu. Choose a workflow invocation and press the V-button to expand it. Press the “View Invocation Report” link below the two colored bars (not the printer icon!).

### New stuff v20.09
- [ ] Allow uploading directly from the tool form
- [ ] Workflow import from GA4GH TRS servers

### New stuff v21.01
- [ ] Workflow invocation details. After a workflow has been run, select “Workflow Invocations” from the “User” menu and click on the workflow name to show details.
- [ ] Workflow author and license metadata annotations in the workflow editor
- [ ] Workflow "Best Practices". Lint a workflow by selecting "Best Practices" from the cogwheel menu in the workflow editor
- [ ] Workflow Reports (with visualizations!). Create a report template in the workflow editor and view the report after running the WF.
- [ ] See the disc usage for users on the Admin page
- [ ] Galaxy Training Materials button in the masthead
- [ ] Beta history panel

### Old tests that may be relevant again in the future
- [ ] Click on the “Help” button on “run workflow” page and check if this takes you to a Galaxy page with instructions for the workflow (or to a page that says “Workflow Instructions. ERROR: Unknown NeLS pipeline: xxxx”)
- [ ] Run a Data Manager (admin page)
