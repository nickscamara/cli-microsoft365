# planner tenant settings list

Lists the Microsoft Planner configuration of the tenant

## Usage

```sh
m365 planner tenant settings list [options]
```

## Options

--8<-- "docs/cmd/_global.md"

## Remarks

!!! important
    To use this command you must be a global administrator.

After executing the command `planner tenant settings set`, it can take some time for all changes to propagate across the tenant. Because of this, executing this command right away can return some unexpected results.

## Examples

Lists the Microsoft Planner settings of the tenant

```sh
m365 planner tenant settings list
```

## Response

=== "JSON"

    ```json
    {
      "id": "1",
      "isPlannerAllowed": true,
      "allowCalendarSharing": true,
      "allowTenantMoveWithDataLoss": false,
      "allowTenantMoveWithDataMigration": false,
      "allowRosterCreation": true,
      "allowPlannerMobilePushNotifications": true
    }
    ```

=== "Text"

    ```txt
    allowCalendarSharing               : true
    allowPlannerMobilePushNotifications: true
    allowRosterCreation                : true
    allowTenantMoveWithDataLoss        : false
    allowTenantMoveWithDataMigration   : false
    isPlannerAllowed                   : true
    ```

=== "CSV"

    ```csv
    isPlannerAllowed,allowCalendarSharing,allowTenantMoveWithDataLoss,allowTenantMoveWithDataMigration,allowRosterCreation,allowPlannerMobilePushNotifications
    1,1,,,1,1
    ```

=== "Markdown"

    ```md
    # planner tenant settings list

    Date: 4/2/2023

    ## 1

    Property | Value
    ---------|-------
    id | 1
    isPlannerAllowed | true
    allowCalendarSharing | true
    allowTenantMoveWithDataLoss | false
    allowTenantMoveWithDataMigration | false
    allowRosterCreation | true
    allowPlannerMobilePushNotifications | true
    disallowedSharedWithContainerTypes | []
    ```
