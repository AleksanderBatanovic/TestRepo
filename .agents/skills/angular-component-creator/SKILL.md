---
name: angular-component-creator
description: Create and integrate Angular components in an existing application or library when the user requests a new UI component, page, or component scaffold.
---

# Angular component creator

Create a working Angular component in the user's target project. When this skill is read from another repository, that repository supplies instructions; it is not the destination for the component.

## Identify the target and conventions

Read applicable AGENTS.md instructions, package.json, the lockfile, angular.json when present, relevant TypeScript configuration, and nearby components and their consumers. Determine the installed Angular version, package manager, target application or library, and intended directory.

Match the target feature's naming, selector prefix, standalone or NgModule structure, template and stylesheet arrangement, UI library, translation conventions, and input/output patterns. Angular workspaces may contain multiple projects; pass the exact configured project name to generators and build commands.

Infer the component name, location, and behavior from the request and project context. Ask only for a missing decision that materially affects implementation. If no Angular project exists at the target, clarify whether the user wants a code example or a new application before scaffolding an application.

## Create the component

Use the project's installed Angular CLI or workspace generator when suitable. Use its help and a dry run when paths or options are uncertain. Do not download a newer CLI through an unpinned runner. Choose supported options from the installed version and project configuration rather than relying on current CLI defaults.

Write files directly when a generator is unavailable or unsuitable. Respect existing files and concurrent edits; do not overwrite a component with the same name.

Implement the requested behavior in TypeScript, HTML, and the project's chosen style format. Use APIs supported by the installed Angular version. Account for version-dependent standalone defaults; set the standalone option explicitly when needed to avoid an ambiguous declaration.

Keep component inputs and emitted events typed. Reuse existing services, domain types, shared components, theme tokens, and UI controls. Follow the feature's state and change-detection patterns; avoid copying legacy workarounds when they conflict with the new behavior. Handle subscription or listener cleanup when the component owns them. Use semantic controls, accessible names, and keyboard behavior for new interactions. For data-driven UI, cover loading, empty, and error states when relevant to the request.

## Integrate where requested

For standalone components, include the dependencies used by their templates and import the component into its intended consumer. For NgModule components, declare it in the correct module and export it only when consumers need that. Do not declare a standalone component in an NgModule.

Wire the parent template, route, or library public export when required by the requested use. A reusable component does not inherently need a new route. If only a scaffold is requested, create the scaffold and provide a minimal usage example.

Keep integration changes focused on making the new component usable. Do not upgrade Angular, refactor unrelated components, or add a new UI framework as part of component creation.

## Verify and report

Run the target project's available checks that cover TypeScript and Angular template compilation, plus relevant lint and behavioral tests. Add or update tests for meaningful component behavior when warranted or required by the project; avoid tests that merely repeat the scaffold. Check responsive layout and interactions in an available preview when the task includes visible UI behavior.

If dependencies, runtime, or a preview are unavailable, inspect what is accessible and state which checks remain unverified. Reading remote GitHub files does not establish that a build or test ran.

Report the files created or changed, how to use the selector or route, and the actual check results. Invoking this skill does not itself authorize committing, pushing, or publishing changes.

## Angular references

Consult documentation for the installed version when an API or generator option is uncertain:
- [Component anatomy](https://angular.dev/guide/components)
- [Component generator](https://angular.dev/cli/generate/component)
