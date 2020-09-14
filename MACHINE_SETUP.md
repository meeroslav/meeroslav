# Setting up the new computer

## Install apps

## Other settings

### Configure `Home` and `End` keys for full keyboard on `Mac`

Create new `DefaultKeyBinding.dict` file in Library:
```
sudo bash 
mkdir -p ~/Library/KeyBindings ; cd ~/Library/KeyBindings
vim DefaultKeyBinding.dict
```

Copy the following content:
```
{
  /* Remap Home / End keys */
  /* Home Button*/
  "\UF729" = "moveToBeginningOfLine:"; 
  /* End Button */
  "\UF72B" = "moveToEndOfLine:"; 
  /* Shift + Home Button */
  "$\UF729" = "moveToBeginningOfLineAndModifySelection:"; 
  /* Shift + End Button */
  "$\UF72B" = "moveToEndOfLineAndModifySelection:"; 
  /* Ctrl + Home Button */
  "^\UF729" = "moveToBeginningOfDocument:"; 
  /* Ctrl + End Button */
  "^\UF72B" = "moveToEndOfDocument:"; 
  /* Shift + Ctrl + Home Button */
  "$^\UF729" = "moveToBeginningOfDocumentAndModifySelection:";
  /* Shift + Ctrl + End Button*/
  "$^\UF72B" = "moveToEndOfDocumentAndModifySelection:"; 
}
```

Original setup from [medium post](https://medium.com/@elhayefrat/how-to-fix-the-home-and-end-buttons-for-an-external-keyboard-in-mac-4da773a0d3a2)
