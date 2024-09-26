# Kai ide plugin developer experience




First
```mermaid
sequenceDiagram
  plugin ->> analyzer: Choose instance
  plugin ->> kai: Choose instance

  plugin ->> analyzer: Ask for analysis
  analyzer ->> plugin: Stream issues
  analyzer ->> plugin: Stream code diagnostics

```

Second
```mermaid
erDiagram

```
