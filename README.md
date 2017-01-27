# How to change the color of right sidebar (miniMap) in Sublime Text 3
 ![](https://raw.githubusercontent.com/kujiy/how-to-change-sublime-minimap-color/master/0308-04.png)

1. Check your current default theme name

    ![](https://raw.githubusercontent.com/kujiy/how-to-change-sublime-minimap-color/master/0308-07.png)

    > Preferences > setting - Default

    Find "theme" 

    ![](https://raw.githubusercontent.com/kujiy/how-to-change-sublime-minimap-color/master/0308-11.png)
    
    >    "theme": "Default.sublime-theme",

    I define the theme name as *THEME_NAME* for only this article.

1. Check your custom theme name

    ![](https://raw.githubusercontent.com/kujiy/how-to-change-sublime-minimap-color/master/0308-08.png)

    > Preferences > setting - User

    Find "theme" 

    Is there no theme? Okay, you're using *THEME_NAME* you saw earlier.
    If you saw a theme definition in here, you're using it insted of *THEME_NAME* (that is overwritten).
    Now let me re-define *THEME_NAME* if you found your custom theme here.

1. Make a overwriting-conf file for the theme.

1. Open the User folder

    ![](https://raw.githubusercontent.com/kujiy/how-to-change-sublime-minimap-color/master/0308-09.png)
    
    >  Preferences > Browse-packages 

    Finder or explorer will open `package` folder.
    Open `User` folder in that.

1. **Create a new file** named `*THEME_NAME*.sublime-theme` .
    Put lines below into the file.

    ```
    [
        {
            "class": "minimap_control",
            "settings": ["always_show_minimap_viewport"],
            "viewport_color": [253, 180, 30, 146],
            "viewport_opacity": 1.0,
        },

        {
            "class": "minimap_control",
            "settings": ["!always_show_minimap_viewport"],
            "viewport_color": [253, 180, 30, 146],
            "viewport_opacity": { "target": 0.0, "speed": 4.0, "interpolation": "smoothstep" },
        },

        {
            "class": "minimap_control",
            "attributes": ["hover"],
            "settings": ["!always_show_minimap_viewport"],
            "viewport_opacity": { "target": 1.0, "speed": 20.0, "interpolation": "smoothstep" },
        },
    ]

    ```
    The file name should be `*THEME_NAME*.sublime-theme`.
    If it was default, should be `Default.sublime-theme `.
    If you're using `Soda Dark 3` theme, should be `Soda Dark 3.sublime-theme`.

    Make sure you must place the file into Packages/User folder.
    
    ![](https://raw.githubusercontent.com/kujiy/how-to-change-sublime-minimap-color/master/0308-06.png)
    
    Perhaps you can just run this command below.
    
          notepad %HOMEPATH%\AppData\Roaming\Sublime Text 3\Packages\User\Default.sublime-theme

1. Restart your Sublime Text 3.

    Congrats. Now you can see the minimap clearly!

# Exapmles
[Here is my samples.](https://github.com/kujiy/how-to-change-sublime-minimap-color/tree/master/samples)

Make sure you must place them correct `Packages/User` folder.

On my windows 8.1 machine, it should be here.

`%HOMEPATH%\AppData\Roaming\Sublime Text 3\Packages\User\Default.sublime-theme`
`C:\Users\USERNAME\AppData\Roaming\Sublime Text 3\Packages\User\Default.sublime-theme`



# Thanks
@sergioFC

http://stackoverflow.com/questions/25239473/how-to-change-the-color-of-right-sidebar-minimap-in-sublime


