
# 🧠 Focus To-do List — Stay Organized While Navigating Complex Codebases

**Focus To-do List** is a Visual Studio 2022 extension designed to help developers stay focused and organized when working with large and complex codebases.

## 🚀 Why Focus To-do List?

When maintaining or extending a large solution, it's easy to lose track of where you are, what you've already analyzed, and what still needs attention. Like many developers, I used to leave temporary comments in the code or add UI text just to confirm I was in the right place. But sometimes, I forgot to remove those changes—and they made it to production. 😬

**Focus To-do List** was born out of that frustration. It gives you a structured way to track your thoughts, tasks, and code references—without cluttering your codebase.

## ✅ Requirements
- Visual Studio 2022 (Community, Professional, or Enterprise)
- **Compatible with Visual Studio 2026 Insiders**

## ✨ Features

- **Multiple To-do Lists per Solution**  
  Organize your work by creating as many lists as needed for different tasks, features, or modules.

- **Two Item Types**  
  ✅ *To-do Items* with checkboxes to mark completion  
  📝 *Note Items* for general comments or reminders

- **Code Linking**  
  Link any item to a specific line of code. Double-click to jump directly to it.

- **Breakpoint Monitoring**  
  Enable *Monitor Breakpoint Hits* to automatically highlight the related item when a breakpoint is hit.

- **Color Customization**  
  Use the built-in color picker or define your own colors via the `CustomColors.txt` file.

- **Categorization & Grouping**  
  Assign categories to items and group them for better organization.

## 🛠 Installation

1. Download and install the extension from the [Visual Studio Marketplace](https://marketplace.visualstudio.com/).
2. Open Visual Studio 2022.
3. Go to `Extensions > Manage Extensions` and search for "Focus To-do List".
4. Install and restart Visual Studio.


## ▶️ Usage

### 🪟 Opening the Extension for the First Time
When opening the extension for the first time, it will appear docked as a tab next to the Solution Explorer.

![Opening the Extension](https://github.com/pablo-gutierrez/focus-todo-docs/blob/main/assets/opening.gif?raw=true)

### 📝 Creating a New List
By default, a list named "Main_ToDoList" is automatically created for each solution.
You can also create additional lists by clicking the "New List" button and assigning them a title.

![Creating a New List](https://github.com/pablo-gutierrez/focus-todo-docs/blob/main/assets/CreatingANewList.gif?raw=true)

### 📂 Selecting an Existing List
Use the dropdown menu to select from all the lists created for the current solution.
The extension remembers the last selected list for each solution, so you can quickly resume where you left off.

![Selecting a List](https://github.com/pablo-gutierrez/focus-todo-docs/blob/main/assets/selectinglist.gif?raw=true)

### ➕ Adding a New Item
Click the '+' button to add a new item to the selected list.
Use the checkbox labeled "Is to-do item" to specify whether the new item is a To-do or a Note.

![Adding a New Item](https://github.com/pablo-gutierrez/focus-todo-docs/blob/main/assets/addingitem.gif?raw=true)

### ✏️ Editing an Item
To edit an existing item, simply select it from the list. Its details will appear in the To-do Editor—the same section used to create new items. Here, you can modify all aspects of the item, including:

- Text
- Category
- Color
- Item type (To-do or Note)
- Linked line of code

To save your changes, click the pencil icon button.    
Since the editor is shared for both creating and editing items, clicking the '+' button instead of the pencil will create a copy of the selected item. This behavior is intentional and designed to make duplication easier.

![Linking to Code](https://github.com/pablo-gutierrez/focus-todo-docs/blob/main/assets/editing.gif?raw=true)

### 🔗 Linking an Item to a Line of Code
Right-click an item and choose "Link to Code" to associate it with a specific line in your source file. Double-clicking the item will navigate you back to that line.
Since code can change over time and line numbers may shift, the extension also stores an anchor consisting of the content of the linked line and the nearest non-empty line above it.
When you double-click an item, the extension first checks if the content at the original line number still matches the saved anchor. If it doesn't, it scans the file from top to bottom looking for the anchor lines.

- If the anchor is found at a different location, the item will still navigate to the correct line and display a message like "Moved to line X".
- If the anchor cannot be found, the extension will navigate to the original line number and display "Not found", indicating that the content has likely changed or been removed.

This mechanism helps maintain reliable navigation even as the code evolves.

![Linking to Code](https://github.com/pablo-gutierrez/focus-todo-docs/blob/main/assets/linkingitemtocode.gif?raw=true)

### 🗂️ Grouping Items by Category
To keep your lists organized, each item can be assigned to a category. The extension provides 'Category' an editable dropdown, allowing you to either select an existing category or create a new one on the fly. When a new list is created, the default category is "General". Once categories are assigned, items are automatically grouped by category within the list view, making it easier to focus on related tasks.

![Linking to Code](https://github.com/pablo-gutierrez/focus-todo-docs/blob/main/assets/grouping.gif?raw=true)

### ⏱️ Monitoring Breakpoints
When a breakpoint is hit during debugging, the extension can automatically select the related item in the list.
To enable this feature, use the option "Set a breakpoint on the linked line" when linking an item to code.
This option adds a special tag to the breakpoint, allowing the extension to identify and highlight the corresponding item when the breakpoint is triggered.
If the tag is not present, the extension will not be able to associate the breakpoint with any item.

![Linking to Code](https://github.com/pablo-gutierrez/focus-todo-docs/blob/main/assets/breakpoints.gif?raw=true)


### 🎨 Customizing Item Colors
To personalize your items, click the paintbrush icon in the editor to open the color picker. The picker includes a default palette of basic colors, but you can also add custom colors:

Enter a hexadecimal color code (e.g., #0969BA) in the input field.
Click OK to add it to the list.

Custom colors are saved in a file named `CustomColors.txt`, located in the folder created by Visual Studio under your user’s Documents directory. The exact path depends on the installed version of Visual Studio:
`%USERPROFILE%\Documents\Visual Studio [Version]\Focus To-Do List`

You can also manually edit the `CustomColors.txt` file to add multiple colors—one per line. If you choose this method, make sure to close and reopen Visual Studio for the changes to take effect.

![Linking to Code](https://github.com/pablo-gutierrez/focus-todo-docs/blob/main/assets/colors.gif?raw=true)

# ⚙️ Configuration Options
Focus To-do List offers several customization options accessible via Tools > Options > Focus To-do List in Visual Studio.

## 📁 Storage Location
By default, all to-do lists are stored as JSON files in the following folder:
`%USERPROFILE%\Documents\Visual Studio [Version]\Focus To-Do List`

You can change this folder from the extension's settings. Note that changing the storage location requires restarting Visual Studio for the changes to take effect.

##📝 Logging
You can enable or disable internal logging to help with debugging or tracking extension behavior.

## 🔍 Breakpoint Monitoring
Toggle the Breakpoint Monitoring feature on or off. When enabled, the extension will automatically highlight the related item when a linked breakpoint is hit during debugging.

![Linking to Code](https://github.com/pablo-gutierrez/focus-todo-docs/blob/main/assets/config.gif?raw=true)

## Privacy
Focus To‑do List stores data locally in your environment. It does not transmit your code or items to external services.

## 📄 License

This project is licensed under the MIT License.
