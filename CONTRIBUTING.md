# How to contribute to CTF Handbooks

## Making Changes to the Handbooks

### Structure of the Writerside Folder
```
./Writerside/
├───cfg/
│   ├───buildprofiles.xml
├───images/
│   ├───air.png
│   ├───appenditemname.png
│   ├───...
├───topics/
│   ├───Commonly-Used-Itemstrings-List.md
│   ├───Making-a-Map-for-Capture-the-Flag.md
│   └───...
├───c.list
├───ch.tree
├───v.list
└───writerside.cfg
```
The main folders you would need to know are the [`images`](./Writerside/images) and [`topics`](./Writerside/topics) sub-folders within the [`Writerside`](./Writerside) folder.
- [`images`](./Writerside/images): This folder contains all the image media used in the handbook. When adding new images, place them in this folder.
- [`topics`](./Writerside/topics): This folder is the home to all the Handbook markdown files. When adding new chapters [without using Writerside](#without-using-writerside), make new markdown files for them here.

---

The below sections will introduce you to the two ways in which you can make changes to the content of handbooks: (1) [Using Writerside](#using-writerside) and (2) [Without using Writerside](#without-using-writerside).

### Using Writerside
1. Install [JetBrains Writerside](https://www.jetbrains.com/writerside/) (version `2024.1`, build `241.15989`) *OR* [Writerside IDE Plugin](https://plugins.jetbrains.com/plugin/20158-writerside?_gl=1%2All6kto%2A_ga%2ANDc2OTczNjcxLjE3MTIyNDEwNzM.%2A_ga_9J976DJZ68%2AMTcxMjI0ODM2Ny4yLjEuMTcxMjI0ODgwOS40Ny4wLjA.) (version `2024.07.241.18775.98`) on a compatible JetBrains IDE.
2. [Fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo) this repository and [clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) your forked repository on your local machine.
3. Then, open the cloned repository in the Writerside application or a JetBrains IDE equipped with the Writerside Plugin.
4. Now you can make your changes. Read the [Writerside documentation](https://www.jetbrains.com/help/writerside/getting-started.html#install) to learn how to use it.
5. Please use separate [commits](https://docs.github.com/en/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/about-commits) in which you edit the markdown files and a separate one in which you re-build the website code with your changes.
6. To re-build,
   1. Follow the first step in [building locally](https://www.jetbrains.com/help/writerside/local-build.html).
   2. You can choose any name for the configuration. Leave `Allow multiple instances` and `Store as project file` unticked.
   3. Keep the default directory specification (root directory of the project) and click `Run`.
   4. Writerside will generate a compressed archive containing the updated website code. Extract it in the root of the project.
   5. Copy the files in the extracted folder and paste them into the root of the project. This should modify the website code files. If asked to whether replace or skip duplicated files, choose replace.
   6. Delete the extracted build folder and the build archive.
   7. Then, commit the re-build changes. Remember to keep this commit separate from the modification of the markdown content.
7. [Submit your changes](#submitting-changes)

### Without using Writerside
If you are editing without Writerside, the maintainers of CTF handbooks will have to build the website code themselves. You may add new topics or modify existing ones. Modifying is simple enough, but you will have to go through a few steps for adding new topics.

**Adding new topics**:
1. Taking "Foo Bar Test" as a topic name, you will have to first create a `.md` file in the [`topics`](./Writerside/topics) folder as `Foo-Bar-Test.md` with the following contents:
   ```markdown
   # Foo Bar Test
   
   (add your contents here...)
   ```
2. If you were to add the topic using Writerside, it would automatically modify the contents of [`ch.tree`](./Writerside/ch.tree) when adding the new topic. Here though, you'll have to add them manually. Please take note of the structure of topics and sub-topics as well to prevent any errors. For example:
```xml
(...)

<instance-profile id="ch"
                 name="CTF Handbooks"
                 start-page="starter-topic.md">

    <toc-element topic="Foo-Bar-Test.md"/>
    <toc-element topic="starter-topic.md"/>
    (...)
    <toc-element topic="Troubleshooting.md"/>
</instance-profile>
```

After making your changes, you may [submit your changes](#submitting-changes).

---

## Submitting Changes
Please make a [GitHub Pull Request to ctf-handbooks.github.io](https://github.com/CTF-handbooks/ctf-handbooks.github.io/compare) with a clear description of your changes if not explicitly mentioned through the title. Read more about Pull Requests [here](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request).