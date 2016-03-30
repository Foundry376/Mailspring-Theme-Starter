# N1 Theme Starter
The N1 Theme Starter is a basic starter for any theme you want to create for [Nylas N1](http://www.nylas.com/n1), the extensible, open-source email client.

## Getting Started
Creating a new theme in N1 is easy! Here's how you can do it.

1. Fork this repo or download the code. Add a name, display name, title, and description for your theme to `package.json`, and change the directory name to match.

2. Open N1 and install the theme by going to `Nylas N1 > Install New Theme...` and selecting the directory.

3. Choose `Developer > Run With Debug Flags` for easier debugging.

4. Now, you can start playing with the theme! It's installed in `~/.nylas/packages/THEME_NAME`, so open it from there. Most of N1's React components are derived from the core variables defined in `ui-variables.less`, and any changes you make there will override the defaults for N1. You can also add more LESS files in `styles` (ideally, separated into logical components like `thread-list.less`) to make your own specific changes. To reload the theme, just open the console (`Developer > Toggle Developer Tools`) and type `NylasEnv.themes.activateThemes()`.

5. Once you're happy with your theme, check how it looks in the theme picker (`Nylas N1 > Change Theme...`). We use your UI variables to pull the colors, but if you want to add your own selections to the color palette, create a `theme-colors.less` file that includes any of the variables that you want to change, and they'll only affect the theme preview. Here are the variables, on the left, with the part of the theme preview that they match:

    ```
    @background-secondary:     BACKGROUND_COLOR
    @text-color:               TEXT_COLOR, FIRST_SWATCH_COLOR
    @component-active-color:   MIDDLE_SWATCH_COLOR
    @toolbar-background-color: LAST_SWATCH_COLOR
    @panel-background-color:   STRIP_COLOR
    ```

## Structure
```
.
├── styles                 # All stylesheets
│   ├── ui-variables.less  # UI variables that override N1's defaults
│   ├── theme-colors.less  # Theme colors for theme preview (optional)
├── index.less             # Main LESS file to import your stylesheets
├── package.json           # Metadata about the theme
├── LICENSE.md             # License with usage rights
└── README.md              # Info about your theme and how to use it
```

