# Commitlink hook for pre-commit

## Configuration

* Create your `commitlint` config file in the repo's root, as explained in Commitlint [docs](https://commitlint.js.org/#/reference-configuration).
* Add the following to your `.pre-commit-config.yaml`:
    ```
    - repo: https://github.com/andykenward/commitlint-pre-commit-hook
      sha: v1.0.0
      hooks:
          - id: commitlint
            stages: [commit-msg]
    ```
* If you are using one of Commitlint's [shared configurations](https://commitlint.js.org/#/concepts-shareable-config),
  add it to the `additional_dependencies` parameter of the hooks, i.e:
    ```
    - repo: https://github.com/andykenward/commitlint-pre-commit-hook
      sha: v1.0.0
      hooks:
          - id: commitlint
            stages: [commit-msg]
            additional_dependencies: ['@commitlint/config-conventional']
    ```
- Install the [`commit-msg`](https://pre-commit.com/#pre-commit-for-commit-messages) hook in your project repo:
    ```shell
    pre-commit install --hook-type commit-msg
    ```
