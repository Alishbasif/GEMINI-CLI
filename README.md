# What is Gemini-CLI?
Gemini CLI is an open-source AI agent that runs directly in your terminal. It helps with coding tasks, file operations, and general queries. The tool comes with built-in features and supports MCP servers.

**Free Tier Benefits:**
- 60 requests per minute
- 1,000 requests per day (with personal Google account)

**Why Gemini CLI?**
- Write Code
- Folders Structures
- Write documentations, README.me files
- Run Terminal commands
- Use Tools
- Support MCP Server

## 1- Setup & Installation
Require version of Node.JS is 20+ and higher

```cmd
npm install -g@google/gemini-cli
gemini -v
npm upgrade -g@google/gemini-cli
```

## 2- Starting & Launching
Start Gemini CLI
```cmd
gemini
```

**First time it asks**
1- Theme(light/Dark)
2- Login Method(for Authentication)
  - Google Login(Best for free quota)
  - Gemini API Key (Higher quota)
  -Vertex API (for GCP use)

## 3- Important Commands in Gemini CLI

```cmd
/auth      # Authentication
/help      # All Commands
/docs      # Documentation
/tools     # What tool use
/stats     # session stats
/quit      # Exit
``` 
## 4- File Handling(Super PowerFull)
Use '@' for giving the file name as example.

```cmd
Fix Error in @main.py
Add more infomation in @README.md file
```
## 5- Shell Mode
If you want to run the commands in terminal
```cmd
!                  # Enable shell mode
pwd                # Run commands
ESC                # Exit Shell Mode
```
## 6- Models and Version Selection

**version check**
```cmd
gemini -v          # check current version
gemini --version
```
**Models**
```cmd
gemini -m "gemini-flash-2.5"      # for free users
gemini -m "gemini-pro-2.5"        # for premium users
```
**Note:** Free tier may auto-switch to Flash due to quota limits.

## 7-Single Prompt Mode
How to give prompts: Run without interactive interface

```cmd
# Using prompt parameter
gemini -p "What is the gcloud command to deploy to Cloud Run"

# Using positional prompt (preferred)
gemini "What is the gcloud command to deploy to Cloud Run"
```
## 8- Debug Mode
See detailed execution information:
```cmd
gemini -d                       # Launch with debug
gemini -d -p "your prompt"      # Debug with single prompt
```
**Note:** This is for authentication, context loading, which gemini.md file is used, system memory, tool usuage

## 9- Sessions Memory:
Save session metrics to file:
```cmd
gemini --session-summary "session.txt"
```
**Tracks:**
It saves all the:
Model usage
API calls
Token consumption
Tool usage statistics

## 10- Yolo Mode (Dangerous, Auto-Approved):
```cmd
gemini -y
gemini -yolo
```
## 11- Gemini.md(Your AI Rule File):
This file gives instructions to the AI guides for:
- Coding Style
- Frame Work versions
- Folder Rule
- Tech Preference

### File Hierarchy
*Global:* ~/.gemini/GEMINI.md - Rules for all projects
*Project Root:* Project-wide instructions
*Local:* Subdirectory-specific rules

## View Current Context
```cmd
/memory show        # Display loaded context
/memory refresh     # Reload GEMINI.md files
```
## Example GEMINI.md
```cmd
# Project Guidelines
## Code Style
- Use TypeScript strict mode
- Follow ESLint rules
- 2-space indentation
## Dependencies
- React 18.x
- Node.js 20+
## Testing
- Write tests for all functions
- Use Jest framework
```

## 12- Build-in Tools
```cmd
/tools
```
**Helps to search with comman Tools**
- Google Search
- Read File
- Write File
- mkdir
- shell

*Gemini always takes permission before use them.*

## 13- Common WorkFlows:
### Quick Terminal Help
**git help:**
```cmd
gemini "show me git commands for rebasing"
```
### Generate Code
```cmd
cd my-project
gemini
> Create a REST API with user authentication
```
### Modify Existing Files
```cmd
gemini
> In @app.py, add error handling to all functions
Restore Previous State
gemini -c
> (make changes)
> /restore
> (select checkpoint to restore)
```
### Troubleshooting
```cmd
Model Switches to Flash
Issue: Pro model auto-switches to Flash
Solution: Use Gemini API Key for higher quota
```
### No Context Loading
```cmd
Issue: GEMINI.md not found
Solution: Check file location with gemini -d
```
### Port Already in Use
```cmd
Issue: Server won't start
Solution: Ask Gemini to use different port
```
### Next Steps
This guide covers installation, configuration, and basic usage. Upcoming topics:

### Configuration files (settings.json, .env)
MCP server integration
Custom slash commands
VS Code integration
Advanced context management
### Quick Reference
# Installation
npm install -g @google/gemini-cli

# Launch
gemini                          # Interactive mode
gemini "prompt"                 # Single prompt
gemini -m "model"               # Choose model
gemini -c                       # With checkpointing
gemini -d                       # Debug mode

# Inside CLI
/help                           # Show commands
/tools                          # List tools
/memory show                    # View context
/restore                        # Restore checkpoint
/quit                           # Exit
!                               # Shell mode
@filename                       # Reference file
Pro Tip: Start small, experiment with simple tasks, and gradually add GEMINI.md instructions as you learn what works best for your workflow.

## Best Practices 
### Do:
- Always start Geminifrom project folder.
- Allow tool permission carefully.
- Use Gemini.md for better results.
- Keep Uploaded.

### Don't;
- Don't run from home folder.
- Don't use YOLO mode daily.
- Don't skip permissions.
- Don't Forget updating.


## Practical Example:
**Weather Dashboard
```cmd
Create python flask web app that shows real-time weather data that using the OpenWeatherMap.API(https://api.openweathermap.org/data/2.5/weather) include:
- Home Page
- Search Form
- Temperature, Humidity, Wind
- Error handling
- Bootstrap UI
- Auto-reload support 
