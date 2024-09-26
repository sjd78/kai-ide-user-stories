# Configuration and runtime support

Note:
  - Settings is File>Preferences>Settings (or `Ctrl+,`)
  - Configuration of the runtimes is separate from configuration of the analysis

Assumptions:
  - Configuration will reside in a configuration file on the developer's workstation


## Story highlights
  - Configuration of runtime can be on User or Workspace level

  - Select the runtime to setup and configure, options should support:
    - deployed with the extension itself _(as the default)_
    - portable runtime the developer makes available
    - runtime installed to the workstation (by developer or by admins)

  - Configure the server
    - Standard configuration view pattern is ok
    - Support storing secretes needed by the runtime
      - Support logging in to services (e.g. login to LLM proxy)
      - Support storing already known / manually generated API keys
    - __Concern__: In a large corporate environment, developers are unlikely to have keys to directly access a model or even understand what a model is. A guided login to some kind of llm provider at a known URL is preferred.

  - Verification of configuration covered under the [startup and keep alive](./manage_runtime.md) story


## Consideration
Open Questions:
How are credentials/keys going to be stored?
How is authentication going to be handled?
How will the client consume previously solved examples from Konveyor?

