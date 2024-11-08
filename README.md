>[!important]
>The contents of this repo is moved to https://github.com/konveyor/editor-extensions via https://github.com/konveyor/editor-extensions/pull/94.  All further updates will be made there.
>

# Summary statement

The Kai ide experience focuses on the common habits of a developer who needs to migrate a project to a new technology.

Analysis provides issues.  Issues contain incidents.  All of the incidents in all of the issues need to be resolved in order to migrate to a new technology.  The tooling should encourage the developer to focus on making changes at the issue level.  Scoping work to a single issue can help to keep both the set of changes needed at any one time smaller, and developer cognitive load low.

From an identified set of issues, the developer will commonly want to:
  1. Fix a single issue in a single source file
  2. Fix a single issue across all affected files
  3. Fix all issues in a single source file
  4. Fix all issues across all files

Fixing a single issue in a single source file is the common linter/codemod pattern.  A problem is highlighted in the editor.  Activating the code actions at that point displays more information about the issue and allows requesting a codemod to fix the issue.

Fixing a single issue across all affected files is a broader operation.  This is the current target of the Kai ide experience.

# Basic information

There will exist:
  - An ide plugin
  - A static code analyzer
  - A Kai instance (generative AI codemod agent) for fixing issues

Questions to keep in mind:
  - What would a cynical developer think?
  - What is part of the tech preview happy path deliverable?
  - How is this different from using a standard linter/codemod process? (eslint, prettier)

Some wider technical assumption:
  - Plugin and the Analyzer/Kai are all individual components
    - The analyzer functionality may be provided by the Kai instance or it may be separate.  As long as the the distinct functionality of those two entities exist, the implementation specific can vary.
  - Analyzer and Kai are orchestrated into a cohesive user experience by the plugin
  - Assume a corporate environment with no admin rights and limited permissions. A few possible runtime permutations to consider:
    - Local portable apps from the plugin dist
    - Local portable apps from the user located outside the plugin dist
    - Local apps installed for the user (e.g. CSB package, headless windows install)
    - Remote apps running somewhere (e.g. Konveyor hub server)

Interaction assumptions:
  - Analysis forward (focus on identifying the issues to guide where to have Kai make fixes)
  - When waiting for an action to complete (analysis or codemod), a visual indication of “action in progress” / “working” should be displayed


## Future considerations

Cascading changes?
  - How to include a suggested change’s potential project level code refactoring needs?
  - What part of a suggested change would be coming from Kai?
  - What additional code refactoring would be required to related files if a suggested change is applied?

How to iterate with the suggested change


# User Experience/Stories/Flow

The high-level user stories are as follows:
  - [Configuration and runtime support](./story/configuration_and_runtime_support.md)
  - [Startup and keep alive the analyzer/Kai runtime](./story/manage_runtime.md)
  - [Configure analysis](./story/configure_analysis.md)
  - [Surface analysis results](./story/surface_analysis.md)...
    - as file based problems in the normal linter/codemod pattern
    - as issues at the project level potentially spanning multiple files
    - [Help focus the user to select and solve a single issue](./story/focus_on_issues.md)
  - [Iterate on issue resolution](./story/iterate_on_issue_resolution.md)
    - at minimum: interact with Kai on a single issue in a single source file
    - _stretch goal_: interact with Kai on the basis of a single issue that may span multiple source files
    - _future goal_: interact with Kai on the basis of all issues in a single file
    - _future goal_: interact with Kai on the basis of a single issue across all sources
    - _future goal x2_: full project changes

