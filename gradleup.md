##Build a android App using Command
I am always fond of command line and always prefer to use one.

If you are more of a command line guy, here are some tips for you

1. You can always Use command line to create android gradle project.
`android create project -t 1 -n ptop -p /home/nic/andy/projects/ptop -a MainActivity -k in.myspace -g -v 0.11.+`
It will create gradle based android project.
2. You can always have a look at provided tasks using command `gradle tasks` and `gradle tasks --all`.
3. Good starting point specific to gradle android build at http://tools.android.com/tech-docs/new-build-system/user-guide
4. Build dev apk with `./gradlew installDebug`. but this will required you to run app manually.
5. Here is a relief, you can run app in single shot by adding gradle task.
```python
task appStart(type: Exec, dependsOn: 'installDebug') {  
  commandLine 'adb', 'shell', 'am', 'start', '-n', 'in.myspace/.MainActivity'
}
```
Now you can build and deploy project with command `./gradlew appStart` from project root.


Happy Coding.!!!
