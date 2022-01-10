## Polybar-themes

### Rofi menus have the wrong backgrounds

This can be fixed by running the below in ~/.config/polybar/theme/scripts/rofi in zsh
Thanks to this [person](https://github.com/adi1090x/polybar-themes/issues/143#issuecomment-997382579) and a for loop

```zsh
for x (*.rasi); do cat $x | sed "s/element-icon\s*{$/element-icon {\n    background-color:  @al;\n    text-color: inherit;\n/g" | sed "s/element-text\s*{$/element-text {\n    background-color:  @al;\n    text-color: inherit;\n/g" | tee $x; done
```
