# Example: Removing a Feature Without Historical Residue

## Task contract

Remove the deprecated export button from the settings page. Preserve the remaining settings, update the page layout, and keep tests for supported export behavior elsewhere in the product.

## Proportionate change

- remove the button and its event wiring;
- remove styling that is unused after the deletion;
- update the settings-page test to reflect the current controls;
- run the existing test and build commands;
- describe the resulting settings page in the handoff.

## Disproportionate change

- add a detector that fails whenever the old button name appears;
- add a repository-wide deny-list for the old feature;
- add documentation explaining that the button is absent on every page;
- add tests whose only assertion is that the abandoned button never returns;
- write a memory entry about the user's dislike of the old button.

The second group may be justified by an independent migration or compatibility contract, but removal alone is not enough evidence.

## Review question

Would the changed files still be justified if the earlier conversation were unavailable? If yes, the change probably belongs to the final state. If no, it is likely historical residue.
