Reflection: “One thing that surprised me about what’s inside the .git folder was …”
Personally, I was not too suprised that such things as the files committed and information on my commit were saved, I expected Git and VS Code to keep track of such information for posterity.
However, I was surprised that information on the author of the repo as well the committer were recorded as well. As someone keen on maintaining privacy I certainly did not expect to see my name pop up in the console.
And while not directly related to the contents of the .git folder I suffered a serious headache using cat-file to access the data behind the hashes, for whatever reason Powershell/VS Code refused to access the data and I needed to use Git Bash.
Even then Git Bash was very particular as to how the hashes were input so for posterity my process was:
     Enter: [ find .git/objects -type f ] into the console
     Then enter: [ find .git/objects -type f | awk -F/ '{print $3$4}' ] into the console
     Then copy the first four hash codes listed and save them somewhere
     Then when using cat-file -t/-p I copied and pasted the saved hashes after the code
For whatever reason Git Bash would only accept the hash names when input in that manner.