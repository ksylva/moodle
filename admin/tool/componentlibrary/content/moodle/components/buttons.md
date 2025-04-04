---
layout: docs
title: "Buttons"
description: "Button types used in Moodle"
date: 2020-01-14T16:32:24+01:00
draft: false
weight: 10
tags:
- Available
---


## How to use buttons

Button components are available as part of a Moodle form, as a single button functioning as a form submit or triggering a JavaScript action. Buttons used in Moodle are based on the [Bootstrap buttons]({{< docsref "/components/buttons" >}}).

The most used buttons types in Moodle are:

## Example

{{< example >}}
<button type="button" class="btn btn-primary">Primary Button</button>
<button type="button" class="btn btn-secondary">Secondary Button</button>
<button type="button" class="btn btn-danger">Danger Button</button>
<button type="button" class="btn btn-outline-secondary">Outline Button</button>
{{< /example >}}

### Primary buttons

{{< example show_markup="false">}}
<button type="button" class="btn btn-primary">Primary Button</button>
{{< /example >}}

For the primary/most used action on the page use a primary button.
For each for or UI component there should only be one primary button.

### Secondary buttons

{{< example show_markup="false">}}
<button type="button" class="btn btn-secondary">Primary Button</button>
{{< /example >}}

Secondary buttons are used for the the cancel options on a form or as a button that is always visible (blocks editing on)

### Danger buttons.

{{< example show_markup="false">}}
<button type="button" class="btn btn-danger">Primary Button</button>
{{< /example >}}

Use a danger button when the primary action is a potentially dangerous action, like deleting a contact in the messaging interface.

### Outline buttons

{{< example show_markup="false">}}
<button type="button" class="btn btn-outline-secondary">Primary Button</button>
{{< /example >}}

Outline buttons are used for buttons that controll part of the user interface, like filters on a table or the display type on the user dashboard. Outline buttons look more subtle than secondary buttons and do not distract the user from the main user interface too much.

### Subtle buttons

{{< example >}}
<button type="button" class="btn btn-subtle-secondary">Subtle Secondary</button>
<button type="button" class="btn btn-subtle-success">Subtle Succcess</button>
<button type="button" class="btn btn-sm btn-subtle-success">Subtle Succcess Small</button>
{{< /example >}}

The subtle class is designed to create buttons that offer a balance between the visual prominence of standard buttons and the minimalism of outline buttons. This class aims to provide a softer, more understated appearance compared to regular buttons while still maintaining more visual presence than outline buttons.

### Icon buttons

{{< example >}}
<button type="button" class="btn btn-icon">
    <i class="icon fa fa-ellipsis-vertical fa-fw" title="Edit" role="img"></i>
</button>
<button type="button" class="btn btn-icon text-bg-danger">
    <i class="icon fa fa-trash-can fa-fw" title="Delete" role="img"></i>
</button>
<button type="button" class="btn btn-icon icon-size-4">
    <i class="icon fa fa-user fa-fw" title="User" role="img"></i>
</button>
<button type="button" class="btn btn-icon icon-size-5">
    <i class="icon fa fa-user fa-fw" title="User" role="img"></i>
</button>
{{< /example >}}

The `.btn-icon` class styles buttons that contain only an icon, providing a visually appealing and compact design for icon-only buttons. This class is ideal for creating minimalistic, icon-based interactions within your UI.

The `.btn-icon` class standardizes icon button styles using the `$btn-icon-border-radius` variable in variables.scss. While this ensures consistency, the `.rounded-circle` Bootstrap class can still be used for legacy support, though it's discouraged for new designs.

## Adding buttons to a page

### Using the single_select renderer

The ```single_button()``` renderer allows you to quickly add a button with an action to a page without having to write a template for the page. Single select buttons are added as miniature forms that can pass custom form data.

{{< php >}}
    $url = new moodle_url("$CFG->wwwroot/my/index.php", $params);
    $button = $OUTPUT->single_button($url, $editstring);
    $PAGE->set_button($resetbutton . $button);
{{< / php >}}

<iframe src="../../../../examples/singlebuttons.php" style="overflow:hidden;height:50px;width:100%;border:0" title="Single button examples"></iframe>

### Button links

Links can be style to look like buttons, the action for this button is to simply navigate to some other page

{{< example >}}
<a href="#next" class="btn btn-secondary">Next Page</a>
{{< /example >}}

### Action buttons

Action buttons have a data-action and are usually linked to a JavaScript eventlistener that will do something on button click.

{{< example >}}
<button data-action="show-fun-thing" class="btn btn-secondary">Click me</button>
{{< /example >}}


### UX tips

Primary buttons have a higher visual weight and attracts most attention it should be used for the default action on a page.

Use primary buttons for the positive action on the page, for example "Save" or "Submit" when working on an assignment

{{< example >}}
<div class="row">
    <div class="col-5">
        <div class="card mb-2">
            <div class="card-body">
                <strong>Save Changes?</strong>
                <div class="d-flex">
                    <button type="button" class="btn btn-secondary me-1">Cancel</button>
                    <button type="button" class="btn btn-primary me-1">Save</button>
                </div>
            </div>
        </div>
    </div>
    <div class="col-5">
        <div class="card mb-2">
            <div class="card-body">
                <strong>Delete profile</strong>
                <div class="d-flex">
                    <button type="button" class="btn btn-primary me-1">Cancel</button>
                    <button type="button" class="btn btn-secondary">Delete</button>
                </div>
            </div>
        </div>
    </div>
</div>
{{< /example >}}

In case of more dangerous actions, like deleting something the having stiling the Cancel button as the primary button could be a good choice

Bootstrap classes are used to style Buttons, the most used styles are:

{{< example >}}
<button type="button" class="btn btn-primary">Primary buttons</button>
<button type="button" class="btn btn-secondary">Secondary buttons</button>
{{< /example >}}

### Button text

The meaning of buttons must be very clear.

{{< example show_markup="false">}}
<div class="row">
    <div class="col-5">
        <div class="card mb-2">
            <div class="card-body">
                <strong>Save Changes?</strong>
                <p>Would you like to not save your changes before exiting?</p>
                <div class="d-flex">
                    <button type="button" class="btn btn-primary me-1">Yes</button>
                    <button type="button" class="btn btn-secondary">No</button>
                </div>
            </div>
        </div>
        <div class="alert alert-warning">Avoid generic 'OK' or 'Yes', avoid confusing phrases</div>
    </div>
    <div class="col-5">
        <div class="card mb-2">
            <div class="card-body">
                <strong>Save Changes</strong>
                <p>Would you like to save your changes before exiting?</p>
                <div class="d-flex">
                    <button type="button" class="btn btn-primary me-1">Save</button>
                    <button type="button" class="btn btn-secondary">Discard</button>
                </div>
            </div>
        </div>
        <div class="alert alert-success">Avoid generic 'OK' or 'Yes', avoid confusing phrases</div>
    </div>
</div>
{{< /example >}}
