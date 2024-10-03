# Configure Analysis

A developer will need to choose the options to apply for analysis of their project.  They need to consider where they are coming from and where they are going.  Selection of an appropriate analysis configuration for a project is very important for the accurate and useful discovery and resolution of issues.

The plugin will provide an analysis configuration to the analyzer/Kai server.  The analysis configuration may be changed at any time by the developer and the analyzer/Kai server will need to readjust.

Konveyor web UI provides a robust guided build of an analysis task.  Much of the configuration help is not available when using the current kantra CLI.  The plugin needs to include guided selection of analysis configurations.


## Story Highlights
  - Analysis configuration should be __profile__ based...
    - A profile is defined as a bundle of analyzer options...
      - source tech,
      - target tech,
      - rule labels,
      - custom rules
    - Follow a similar pattern to the way run/debug configurations are stored
    - Anticipate a single configuration file with multiple entires

  - Only a single profile will be active at any given time

  - The developer may change the active profile at any time

  - The developer may define their own analysis configuration profiles

  - Provide a set of preset analysis configurations[^1]
    - presets would be based on what is packaged with the extension
    - presets would be provided for the common migration targets (e.g. JEE to Quarkus, or Spring Framework to Spring Boot)

  - Status indication in vscode's status bar (in addition to its runtime management function) should
    - Indicate the active analysis configuration profile at a glance (can be similar to how git shows the current branch)
    - Hovering the static indicator shows the full name of the analysis configuration profile
    - Clicking the status indication...

  - Command Palette
    - Select analysis configuration
    - Create/Edit analysis configurations

  - After initial install / start of the extensions, an analysis configuration must be selected before any issues can be discovered and presented
    - Status indicator should show "Configuration required" as necessary
    - Custom views should show "Configuration required" as necessary


## Considerations

[^1]: Comparing to Konveyor HUB and UI, we can emulate the [hub target entities](https://github.com/konveyor/tackle2-hub/blob/6b050e7be9e651f12e9c64b2b685a856f8e1e970/api/target.go#L237-L247) and provide an experience similar to what is asked for in the [target platforms](https://github.com/konveyor/enhancements/tree/master/enhancements/archetype-target-platforms) enhancement.

