# spo file retentionlabel ensure

Apply a retention label to a file

## Usage

```sh
m365 spo file retentionlabel ensure [options]
```

## Options

`-u, --webUrl <webUrl>`
: URL of the site where the retentionlabel from a file to apply is located

`--fileUrl [fileUrl]`
: The site- or server relative URL of the file that should be labelled. Specify either `fileUrl` or `fileId` but not both.

`i, --fileId [fileId]`
: The UniqueId (GUID) of the file that should be labelled. Specify either `fileUrl` or `fileId` but not both.

`--name <name>`
: Name of the retention label to apply to the file.

`-a, --assetId [assetId]`
: A Compliance Asset Id to set on the item when it's labeled. See below for more information.

--8<-- "docs/cmd/_global.md"

## Remarks

You can also use [spo listitem retentionlabel remove](./../../../cmd/spo//listitem/listitem-retentionlabel-remove.md) for removing the retentionlabel from a listitem.

The `--assetId` option has to do with event-based retention. Event-based retention is about starting a retention period when a specific event occurs, instead of the moment a document was labeled or created.

## Examples

Applies a retention label to a file based on the label name and the fileUrl

```sh
m365 spo file retentionlabel ensure --webUrl https://contoso.sharepoint.com/sites/project-x --fileUrl '/Shared Documents/Document.docx' --name 'Some label'
```

Applies a retention label to a file based on the label name and the fileId

```sh
m365 spo file retentionlabel ensure --webUrl https://contoso.sharepoint.com/sites/project-x --fileId '26541f96-017c-4189-a604-599e083533b8' --name 'Some label'
```

Applies a event-based retention label to a file and updates the Asset Id field

```sh
m365 spo file retentionlabel ensure --webUrl https://contoso.sharepoint.com/sites/project-x --fileId '26541f96-017c-4189-a604-599e083533b8' --name 'Some label' --assetId 'XYZ'
```

## Response

The command won't return a response on success.
