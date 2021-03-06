#### Using RepoSense

<div id="main">

In previous semesters we asked students to annotate all their code using special `@@author` tags so that we can extract each student's code for grading. This semester, we are trying out a tool  called RepoSense that is expected to **reduce the need for such tagging**, and also make it **easier for you to see (and learn from) code written by others**.

<pic src="https://github.com/reposense/RepoSense/raw/release/docs/images/report.png" alt="Logo">
  <sub>Figure: RepoSense Report Features</sub>
</pic>

**1. View the current status of code authorship data:**

* **The report generated by the tool is available at [Project Code Dashboard](https://nus-{{ module | lower }}-{{ semester | lower }}.github.io/{{ module | lower }}-dashboard).** The feature that is most relevant to you is the _Code Panel_ (shown on the right side of the screenshot above). It shows the code attributed to a given author. You are welcome to play around with the [other features](https://github.com/reposense/RepoSense/blob/release/docs/UserGuide.md#interpreting-the-report) (they are still under development and will not be used for grading this semester).
* Click on your name to load the code attributed to you (based on Git blame/log data) onto the code panel on the right.
* If the code shown roughly matches the code you wrote, all is fine and there is nothing for you to do.

**2. If the code does not match:**

* Here are the possible reasons for the code shown not to match the code you wrote:
  * the git username in some of your commits does not match your GitHub username (perhaps you missed our instructions to set your Git username to match GitHub username earlier in the project, or GitHub did not honor your Git username for some reason)
  * the actual authorship does not match the authorship determined by git blame/log e.g., another student touched your code after you wrote it, and Git log attributed the code to that student instead

* In those cases,
  * Install RepoSense (see the [Getting Started](https://github.com/reposense/RepoSense/blob/release/docs/UserGuide.md#getting-started) section of the RepoSense User Guide)
  * Use the two methods described in the RepoSense User Guide section [Configuring a Repo to Provide Additional Data to RepoSense](https://github.com/reposense/RepoSense/blob/release/docs/UserGuide.md#configuring-a-repo-to-provide-additional-data-to-reposense) to provide additional data to the authorship analysis to make it more accurate.
   * If you add a `config.json` file to your repo (as specified by one of the two methods),
     * **Please use the [template json file given in the module website](https://nus-cs2103-ay1819s1.github.io/cs2103-website/admin/reposenseConfigTemplates.html)** so that your display name matches the name we expect it to be.
     * If your commits have multiple author names, specify all of them e.g., `"authorNames": ["theMyth", "theLegend", "theGary"]`
     * Update the line `config.json` in the `.gitignore` file of your repo as `/config.json` so that it ignores the `config.json` produced by the app but not the `_reposense/config.json`.
   * If you add `@@author` annotations, please follow the guidelines below:

<div class="indented-level3">
<panel header="Adding `@@author` tags to indicate authorship">
  <include src="reposenseAuthorAnnotation.md" />
</panel>
</div>

  * After you are satisfied with the new results (i.e., results produced by running RepoSense locally), push the `config.json` file you added and/or the annotated code to your repo. We'll use that information the next time we run RepoSense (we run it at least once a week).
  * If you choose to annotate code, please annotate code chunks not smaller than a method. We do not grade code snippets smaller than a method.
  * If you encounter any problem when doing the above or if you have questions, please post in the [forum]({{ forum_link }}).

==**We recommend you ensure your code is RepoSense-compatible by v1.3**==

</div>
