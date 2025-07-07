**Version 4.0 | Local File Implementation**    
**Owner:** Geraldine Lee
**Purpose:** Clear, step-by-step instructions for proper local file operations with ClaudeOS project routing capabilities

---

## Available ClaudeOS Local File Operations

### Operation 1: Create Project Folder
**Function:** Creates a new project folder in the ClaudeOS ProjectKnowledge directory
**Command:** `mkdir ClaudeOS/ProjectKnowledge/[foldername]`
**Usage:** For setting up new project directories before creating documents
**Example:** Creates `ClaudeOS/ProjectKnowledge/[foldername]/` directory

### Operation 2: Create Document  
**Function:** Creates a new markdown document with automatic project folder routing  
**Tool:** Write
**Parameters:**
- `file_path` (string) - Full path to document including project folder
**Usage:** For creating new documents in correct project directories

### Operation 3: Update Document    
**Function:** Updates existing document content using Edit tool  
**Tool:** Edit
**Parameters:**
- `file_path` (string) - Full path to existing document
- `old_string` (string) - Content to replace
- `new_string` (string) - New content
**Usage:** For updating or modifying existing documents

### Operation 4: Read Document    
**Function:** Reads existing document content
**Tool:** Read
**Parameters:**
- `file_path` (string) - Full path to document
**Usage:** For reading existing documents and verifying content

---

## CRITICAL RULES - READ BEFORE EVERY FILE OPERATION

### Rule 1: Local File System Location
- **ClaudeOS Directory Structure** contains all project management files
- Access files through direct file system paths
- All project routing and document management flows through local file operations

### Rule 2: Project Folder Creation
- **Always create project folder FIRST** before creating documents
- Use `mkdir ClaudeOS/ProjectKnowledge/[foldername]` with exact folder name (no spaces, lowercase)
- Folder will be created in `ClaudeOS/ProjectKnowledge/[foldername]/`
- **Project folder names:**
  - `viableedgeadvisoryboard` - The Viable Edge project
  - `sdaadvisoryboard` - SDA project
  - `clientprojecthydr8` - HYDR8 client project
  - `claudeosmanagement` - ClaudeOS Management project

### Rule 3: Project Folder Routing
- **Always use correct file paths** when creating documents
- Use exact project folder name (no spaces, lowercase)
- Documents will be created in correct project directory via file path
- Folder must exist before documents can be created in it

### Rule 4: Document Identification  
- Documents are identified by **EXACT FILE PATH ONLY**  
- Paths are case-sensitive and must match exactly  
- No partial paths or approximate matches  
- Always verify the exact file path before calling Edit operations

### Rule 5: Document Update Mechanism  
- Edit tool uses find/replace to update specific content sections
- Write tool overwrites ENTIRE document content  
- **WARNING:** Write tool will overwrite and replace existing content completely
- Use Edit tool for partial updates, Write tool for complete rewrites

### Rule 6: Document Existence Verification  
- Never attempt to edit a document that doesn't exist  
- Use Read tool to verify document content before editing
- Create new documents first with Write tool, then modify with Edit tool

### Rule 7: Content Formatting  
- All document content must be formatted in markdown  
- Include proper headers, structure, and formatting  
- Maintain document version information and metadata

### Rule 8: SINGLE FILE OPERATION PROTOCOL
- **CRITICAL:** Perform only ONE file operation per action to prevent failures
- **Never attempt multiple file operations** in a single tool call or response
- **If multiple files need operations:** Use separate, sequential operations
- **Rationale:** Prevents incomplete operations and maintains system stability
- **Exception:** Only combine operations if explicitly requested by user and content is minimal

### Rule 9: SYSTEM CORE FILE RESTRICTIONS
- **ABSOLUTE PROHIBITION:** Regular projects CANNOT update System Core files under any circumstances
- **System Core Files Include:**
  - "ClaudeOS Personal Operating System - Universal Guide" (universal-guide.md)
  - "Claude Project Tool Usage Guide - Local File Operations" (tool-usage-guide.md)
  - Any other universal documents in the `SystemCore` folder
- **ClaudeOS Management Exception:** Only ClaudeOS Management project can update System Core files WITH explicit user approval
- **Violation Consequences:** System instability, cascade failures across all projects, protocol corruption
- **Alternative:** Route System Core update requests through ClaudeOS Management project

---

## Step-by-Step Workflows

### Workflow A: Creating a New Project

**Step 1:** Create the project folder  
```bash
mkdir ClaudeOS/ProjectKnowledge/[project_folder_name]
```

**Step 2:** Create the strategic instructions document  
```
Write
file_path: ClaudeOS/ProjectKnowledge/[project_folder_name]/strategic-instructions.md
content: [Complete strategic instructions content]
```

**Step 3:** Create the project metadata document (MANDATORY)  
```
Write
file_path: ClaudeOS/ProjectKnowledge/[project_folder_name]/project-metadata.md
content: [Complete project metadata content]
```

**Step 4:** Create status reporting document
```
Write
file_path: ClaudeOS/ProjectKnowledge/[project_folder_name]/status-report.md
content: [Complete status report content]
```

**IMPORTANT:** Create each document separately - do not attempt multiple operations in one action.

**Example:**
1. Create Folder: `mkdir ClaudeOS/ProjectKnowledge/newprojectadvisoryboard`
2. Create Instructions: `file_path: ClaudeOS/ProjectKnowledge/newprojectadvisoryboard/strategic-instructions.md`
3. Create Metadata: `file_path: ClaudeOS/ProjectKnowledge/newprojectadvisoryboard/project-metadata.md`
4. Create Status: `file_path: ClaudeOS/ProjectKnowledge/newprojectadvisoryboard/status-report.md`

### Workflow B: Creating Documents in Existing Project

**Step 1:** Verify project folder exists  
- Confirm folder is in ClaudeOS/ProjectKnowledge directory
- Use exact folder name (no spaces, lowercase)

**Step 2:** Create the document with project routing  
```
Write
file_path: ClaudeOS/ProjectKnowledge/[existing_project_folder]/[document-name].md
content: [Complete document content]
```

### Workflow C: Updating an Existing Document

**MANDATORY PRE-CHECK:** Verify document update authorization
1. **Check if document is in YOUR project folder** - Only update documents belonging to your project
2. **Verify document is NOT a System Core file** - System Core files require special authorization
3. **If uncertain about authorization** - Ask user for explicit permission before proceeding

**Step 1:** Read existing document content
```
Read
file_path: ClaudeOS/ProjectKnowledge/[project_folder]/[document-name].md
```

**Step 2:** Update with specific content changes
```
Edit
file_path: ClaudeOS/ProjectKnowledge/[project_folder]/[document-name].md
old_string: [Exact content to replace]
new_string: [New content to replace with]
```

**Critical:** Use Edit for partial updates, Write for complete document replacement

### Workflow D: Reading Document Content

**For verification or content review:**  
```
Read
file_path: ClaudeOS/ProjectKnowledge/[project_folder]/[document-name].md
```

### Workflow E: System Core Update Protocol

**FOR CLAUDEOS MANAGEMENT PROJECT ONLY:**

**Step 1:** Assess Update Need and Impact
- Identify specific operational requirement
- Evaluate effect on all active projects
- Document justification for change

**Step 2:** Request Explicit User Approval
- Present clear recommendation to user
- Explain impact on system-wide operations
- Wait for explicit "yes" authorization

**Step 3:** Execute Single File Update
```
Edit
file_path: ClaudeOS/SystemCore/[system-core-file].md
old_string: [Exact content to replace]
new_string: [Updated content]
```

**Step 4:** Document and Communicate Changes
- Update version numbers appropriately
- Notify affected projects through status reports
- Monitor system-wide impact

**FOR ALL OTHER PROJECTS:**
- **NEVER attempt System Core updates**
- Route requests through ClaudeOS Management
- Focus on project-specific document updates only

---

## Project Folder Routing System

### How ClaudeOS Local File Routing Works
1. **mkdir** creates directory in ClaudeOS/ProjectKnowledge
2. **Write** creates documents with full file paths including project folder
3. **Local file system** manages document placement automatically
4. **Edit** modifies documents using exact file paths
5. **Project boundaries maintained** through folder structure

### ClaudeOS Directory Structure
```
ClaudeOS/
├── ProjectKnowledge/
│   └── [project_folders]/       # Project folders created with mkdir
├── SystemCore/                  # UNIVERSAL DOCUMENTS - RESTRICTED ACCESS
│   ├── universal-guide.md
│   ├── tool-usage-guide.md
│   └── templates/
```

### Project Folder Naming Convention
- **Format:** `[projectname][type]` (no spaces, lowercase)
- **Examples:**
  - `clientproject[name]` (Client projects)
  - `claudeosmanagement` (ClaudeOS Management)
- **Created with:** `mkdir ClaudeOS/ProjectKnowledge/[folder_name]`

### Determining Your Project Folder
**Each project must know its own folder name:**
- Check project metadata document: `project-metadata.md`
- Reference project-specific strategic instructions
- When in doubt, use the ClaudeOS standard naming convention
- **For new projects:** Create folder first with mkdir

---

## Local File System Integration

### File Operation Access Location
- **Location:** ClaudeOS folder structure on local file system
- **Available Tools:** Read, Write, Edit, Bash (for mkdir)

### File Operation Consistency  
- **Reference Authority:** Always consult this document before using file operations
- **Workflow Compliance:** Follow exact step-by-step procedures with project folders
- **Error Prevention:** Verify file paths and use correct project folder names
- **Quality Assurance:** Maintain markdown formatting and proper structure
- **Single Operation Rule:** Perform only one file operation per action
- **System Core Respect:** Never attempt unauthorized System Core updates

### Local File System Integration Benefits
- **Direct file access** through local file system
- **Consistent project routing** through folder structure
- **Simple folder creation** for new project setup
- **Streamlined workflow** from folder creation to document management
- **Error prevention** through single file operation protocol
- **System stability** through proper access controls

---

## Common Errors and How to Avoid Them

### Error 1: "Project Folder Not Found"  
**Cause:** Trying to create documents in non-existent project folder  
**Solution:** Use mkdir to create folder first  
**Prevention:** Always create project folder before creating documents

### Error 2: "File Not Found"  
**Cause:** Incorrect file path used in Read/Edit operations  
**Solution:** Verify exact file path and folder structure  
**Prevention:** Always use complete, exact file paths

### Error 3: "Document Content Lost"    
**Cause:** Using Write tool when Edit tool should be used  
**Solution:** Use Edit for partial updates, Write for complete replacement  
**Prevention:** Read document first, then use appropriate tool

### Error 4: "Path Error"  
**Cause:** Incorrect file path format or missing folders  
**Solution:** Verify complete path including project folder  
**Prevention:** Use format: `ClaudeOS/ProjectKnowledge/[project_folder]/[document].md`

### Error 5: "Wrong Project Folder"  
**Cause:** Incorrect project folder name used  
**Solution:** Verify exact project folder name from metadata document  
**Prevention:** Reference project-specific folder name consistently

### Error 6: "Permission Denied"  
**Cause:** Attempting to access System Core files without authorization  
**Solution:** Route request through ClaudeOS Management  
**Prevention:** Check document authorization before operations

### Error 7: "File System Error"  
**Cause:** Local file system access issues  
**Solution:** Verify ClaudeOS folder structure exists  
**Prevention:** Ensure proper directory setup

### Error 8: "Operation Incomplete"
**Cause:** Multiple operations causing tool failures
**Solution:** Complete one operation at a time, then proceed with next
**Prevention:** Follow single file operation protocol strictly

### Error 9: "System Core Access Denied"
**Cause:** Regular project attempting to update System Core files
**Solution:** Route request through ClaudeOS Management project
**Prevention:** Verify document authorization before any update attempts

---

## File Path Best Practices

### Recommended Format:  
`ClaudeOS/ProjectKnowledge/[project_folder]/[document-name].md`

### Examples:  
- `ClaudeOS/ProjectKnowledge/viableedgeadvisoryboard/strategic-instructions.md`
- `ClaudeOS/ProjectKnowledge/clientprojectabc/status-report.md`    
- `ClaudeOS/ProjectKnowledge/claudeosmanagement/system-updates.md`

### Avoid:  
- Spaces in folder names or file names
- Special characters that might cause file system issues  
- Extremely long paths (keep reasonable length)
- Missing .md extension for markdown files

---

## Troubleshooting Checklist

### Before Using Any File Operation:  
- [ ] Verified ClaudeOS folder structure exists
- [ ] Confirmed exact file path (for reads/edits)
- [ ] Confirmed correct project folder name
- [ ] Ensured project folder exists (create with mkdir if needed)
- [ ] Prepared complete content (for writes)  
- [ ] Checked for proper markdown formatting
- [ ] **Verified single file operation only**
- [ ] **Confirmed document update authorization level**

### If File Operation Fails:  
1. Check ClaudeOS folder structure exists
2. Verify project folder exists (create if missing)
3. Check exact file path spelling and folder name
4. Verify document exists in project folder (for edits)
5. Ensure content is complete and properly formatted  
6. Verify file path format: `ClaudeOS/ProjectKnowledge/[project]/[file].md`
7. **Confirm operation involves only single file**
8. **Verify authorization for document being updated**
9. Retry with identical parameters  
10. If persistent issues, create new document with different name

### After File Operation:  
- [ ] Verify document was created in correct project folder
- [ ] Check content appears correctly  
- [ ] Confirm no content was lost or corrupted
- [ ] Validate project routing worked as expected
- [ ] **Confirm single operation completed successfully**

---

## Quick Reference Commands

### Create New Project:  
```bash
mkdir ClaudeOS/ProjectKnowledge/[new_project_folder_name]
```

### Create New Document:  
```
Write
file_path: ClaudeOS/ProjectKnowledge/[project_folder]/[document-name].md
content: [Complete document content]
```

### Update Existing Document:  
```
Edit
file_path: ClaudeOS/ProjectKnowledge/[project_folder]/[document-name].md
old_string: [Exact content to replace]
new_string: [New content]
```

### Read Document:  
```
Read
file_path: ClaudeOS/ProjectKnowledge/[project_folder]/[document-name].md
```

---

## Examples of Proper File Operations

### Example 1: Creating New Project with Documents (SEQUENTIAL OPERATIONS)
```
1. mkdir ClaudeOS/ProjectKnowledge/newclientprojectabc

2. Write
   file_path: ClaudeOS/ProjectKnowledge/newclientprojectabc/strategic-instructions.md
   content: [Complete strategic instructions content]

3. Write
   file_path: ClaudeOS/ProjectKnowledge/newclientprojectabc/project-metadata.md
   content: [Complete metadata content]

4. Write
   file_path: ClaudeOS/ProjectKnowledge/newclientprojectabc/status-report.md
   content: [Complete status report content]
```

### Example 2: Creating Document in Existing Project  
```
1. Write
   file_path: ClaudeOS/ProjectKnowledge/viableedgeadvisoryboard/marketing-strategy-q3.md
   content: [Complete marketing strategy content]
```

### Example 3: Updating Existing Document  
```
1. Read
   file_path: ClaudeOS/ProjectKnowledge/viableedgeadvisoryboard/status-report.md

2. Edit
   file_path: ClaudeOS/ProjectKnowledge/viableedgeadvisoryboard/status-report.md
   old_string: [Exact content to replace]
   new_string: [Updated content]
```

### Example 4: System Core Update (CLAUDEOS MANAGEMENT ONLY)
```
1. Request explicit user approval for System Core update
2. Wait for explicit authorization
3. Edit
   file_path: ClaudeOS/SystemCore/universal-guide.md
   old_string: [Exact content to replace]
   new_string: [Updated content]
4. Document changes and notify all projects
```

---

## Integration with ClaudeOS System

### Universal System Dependencies
- **ClaudeOS Personal Operating System - Universal Guide:** System architecture and protocols
- **Project-Specific Strategic Instructions:** Each project's unique context and folder name
- **Cross-Project Coordination:** Status documents and intelligence sharing

### Local File System Validation
**Before creating documents, verify:**
1. **ClaudeOS folder structure** exists on local file system
2. **Project folder exists** or create with mkdir
3. **Project folder name** is correct for your specific project
4. **File path format** follows ClaudeOS conventions
5. **Content structure** includes proper metadata and formatting
6. **Single operation scope** - only one file per operation
7. **Update authorization** - confirm permission level for target document

### System Core Updates
**When System Core files are updated:**
- All projects inherit changes automatically through shared file access
- Tool capabilities are enhanced system-wide
- Consistency is maintained across ClaudeOS ecosystem
- New protocols become available to all projects

---

## Security and Safety Protocols

### Document Update Safety
**Before updating ANY document:**
1. **Verify Document is in Project Folder** - Check if document exists in YOUR project's folder  
2. **Check System Core Status** - If document is System Core, verify authorization level
3. **If Document is NOT in Project Folder** = READ ONLY ACCESS (never update)  
4. **If Document IS in Project Folder** = Safe to update within project boundaries
5. **If Document is System Core** = ClaudeOS Management only, with explicit approval
6. **Confirm Single File Operation** = Only one document per operation
7. **When in Doubt** = Ask user for explicit permission before any document updates

### Cross-Project Document Access Rules  
- **READ ACCESS:** All projects can read accessible documents for reference  
- **WRITE ACCESS:** Projects can ONLY update documents in their own project folder
- **SYSTEM CORE ACCESS:** Only ClaudeOS Management with explicit user approval
- **PROJECT ROUTING:** Documents are created in correct project directories via file paths
- **FOLDER CREATION:** Only create folders when setting up new projects
- **SINGLE OPERATION RULE:** One file operation per action to prevent failures
- **USER OVERRIDE:** User can explicitly command cross-project operations when needed

### Local File System Security
- **Folder-based access control** through project directory structure
- **Project boundary enforcement** through file path routing
- **Consistent permission management** across all operations
- **Version control** through git integration for change tracking
- **Operation limits** through single file operation protocol
- **System Core protection** through strict authorization controls

---

**Remember:** These local file operations enable document creation and management with automatic project routing through folder structure, but strategic thinking and business partnership approach remain the primary focus for all content and decision-making. The single file operation protocol and System Core access controls ensure system stability and reliable operations across the entire ClaudeOS ecosystem.

**ClaudeOS Status:** Fully operational with local file management capabilities, project folder creation, centralized document access through local file system, single file operation protocol, and strict System Core access controls.