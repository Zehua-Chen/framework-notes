# Enabling Multiple Windows

To enable multiple windows

- **Using project file**
  1. Go to your project file, click on your target
  2. Go to "General" and then go to "Deployment Info"
  3. Go to "Status Bar Style" and then enable "Supports multiple windows"
- **Using `Info.plist`**
  1. Expand "Information Property List"
  2. Expand "Application Scene Manifest"
  3. Set "Enable Multiple Windows" to "YES"

# Design

- Users should be able to do everything from one window
- Users can bring up more windows if they want
- Users expect document-based, tab-based and some drag-and-drop apps to have
  multiple windows
