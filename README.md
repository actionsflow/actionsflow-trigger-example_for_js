# `@actionsflow/trigger-example_for_js`

This is an [Actionsflow](https://github.com/actionsflow/actionsflow) example trigger.

## Install

```bash
npm i @actionsflow/trigger-example_for_js
```

## Usage

```yaml
on:
  example_for_js:
    param1: value1
```

## Options

- `param1`, optional, describe your param

> You can use [General Config for Actionsflow Trigger](https://actionsflow.github.io/docs/workflow/#ontriggerconfig) for more customization.

## Outputs

This trigger's outputs will be the following object.

An outputs example:

```json
{
  "id": "uniqueId",
  "title": "hello world title"
}
```

You can use the outputs like this:

```yaml
on:
  example_for_js:
    param1: value1
jobs:
  print:
    name: Print
    runs-on: ubuntu-latest
    steps:
      - name: Print Outputs
        env:
          title: ${{ on.example_for_js.outputs.title }}
          id: ${{ on.example_for_js.outputs.id }}
        run: |
          echo "title: $title"
          echo "id: $id"
```
