# Tel Aviv University - Tips

## Printer
Use the following snippet to print in the CS building: (Should work for most PDF and plaintext files)

`cat filename.pdf | ssh username@nova.cs.tau.ac.il lpr -P hpintel`

MacOS Automator (Applescript in ~/Library/PDF Services)
```
on run {input, parameters}
  repeat with i in input
    set cmd to "cat " & quoted form of POSIX path of i ¬
     & " |ssh username@nova.cs.tau.ac.il lpr -P hpintel"
    set theResult to do shell script cmd
  end repeat
  return input
end run
```