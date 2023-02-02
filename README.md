# Email Block for Obsidian [![GitHub tag (latest by date)](https://img.shields.io/github/v/tag/joleaf/obsidian-email-block-plugin)](https://github.com/joleaf/obsidian-email-block-plugin/releases) [![Release Obsidian Plugin](https://github.com/joleaf/obsidian-email-block-plugin/actions/workflows/release.yml/badge.svg)](https://github.com/joleaf/obsidian-email-block-plugin/actions/workflows/release.yml) ![GitHub all releases](https://img.shields.io/github/downloads/joleaf/obsidian-email-block-plugin/total)

This plugin lets you plan small emails inside your [Obsidian](https://www.obsidian.md) notes.

## Install ..

### .. automatically in Obsidian

1. Go to **Community Plugins** in your Obsidian Settings and **disable** Safe Mode
2. Click on **Browse** and search for "Email Block"
3. Click install
4. Toggle the plugin on in the **Community Plugins** tab

### .. manually from this repo

1. Download the latest [release](https://github.com/joleaf/obsidian-email-block-plugin/releases) `*.zip` file.
2. Unpack the zip in the `.obsidan/plugins` folder of your obsidian vault

## How to use

Add the "email" code block into your note:

... with plain text as body content:

````
```email
to: info@randommail.com
subject: My Subject
body: "Hey info,

  here is some content"
```
````

... with a referenced note as body content:

````
```email
to: info@randommail.com
subject: My Subject
body: [[MyMail4711]]
variables:
  myvar: TestVar
```
````

You can use the `variables` parameter to replace placeholders in your body text with the variable values.
To include a variable in the body text just add a placeholder `{{myvar}}`.
Variables from frontmatter data can be used as well.

### Parameter

You can customize the view with the following parameters:

| Parameter  | Description                                                            | Values                     |
|------------|------------------------------------------------------------------------|----------------------------|
| to         | The main receiver of the mail. Multiple receiver seperated by ",".     | String value               |
| cc         | The cc receiver of the mail. Multiple receiver seperated by ",".       | String value               |
| bcc        | The bcc receiver of the mail. Multiple receiver seperated by ",".      | String value               |
| subject    | The subject of the email.                                              | String value               |
| body       | The body of the email. Plain text or a link to a \[\[NoteFile\]\] (x). | String value               |
| showmailto | Show the "mailto" link after the mail body.                            | true/false (Default: true) |
| variables  | A map of placeholder variables.                                        | YAML Object                | - |

x) Note that no formatting is supported (only new
lines) ([reason](https://stackoverflow.com/questions/5620324/mailto-link-with-html-body)).

### Example

![Example](example/email-block-plugin.gif)

## How to dev

1. Clone this repo into the plugin folder of a (non-productive) vault (`.obsidian/plugins/`)
2. `npm i`
3. `npm run dev`
4. Toggle the plugin on in the **Community Plugins** tab

## Donate

<a href='https://ko-fi.com/joleaf' target='_blank'><img height='35' style='border:0px;height:46px;' src='https://az743702.vo.msecnd.net/cdn/kofi3.png?v=0' border='0' alt='Buy Me a Coffee at ko-fi.com' />
