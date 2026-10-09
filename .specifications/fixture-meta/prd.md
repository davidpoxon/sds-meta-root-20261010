# PRD: Meta-repository delivery fixture spec

The fixture spec the delivery kernel tests deliver in a meta-repository: a root
with one submodule at `sub`. Unit S changes the submodule, so its `repo:sub` label
names it, and unit R changes the root and needs S, so the root stack starts with a
pointer placeholder for `sub`.

## User stories

- **FXM-US-001** As a meta-repository operator, I want the submodule stack and the pointer bump sequenced for me, so that the root pull request goes green unaided.

## Functional requirements

- **FXM-FR-001** The kernel delivers the submodule stack first, then commits the pointer on the root stack's placeholder layer once the submodule stack has merged. _(serves FXM-US-001)_
