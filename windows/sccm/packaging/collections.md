# Collections
## Collection Rules
To edit collection rules, navigate to the desired collection, right click and select **Properties**, then go the **Membership Rules** tab.

### Direct Rules
Direct Rules allow SCCM administrators to explicitly add a device to a collection by name.

### Query Rules
Query Rules allow SCCM administrators to add devices to a collection based on a query.
#### Examples:
    - Populating a collection from an Active Directory Group
        - `select SMS_R_SYSTEM.ResourceID,SMS_R_SYSTEM.ResourceType,SMS_R_SYSTEM.Name,SMS_R_SYSTEM.SMSUniqueIdentifier,SMS_R_SYSTEM.ResourceDomainORWorkgroup,SMS_R_SYSTEM.Client from SMS_R_System where SMS_R_System.SecurityGroupName = "<domain>\\<group name>"`
    - Creating collections of devices with a certain application installed
        - TODO
### Device Category Rule

### Include Collections
Include Collections allow SCCM administrators to add another collection to a collection.

### Exclude Collections
Exclude Collections allow SCCM administrators to exclude one collection for another.

For example, this is useful in scenarios such as an application needing to be scoped to all devices at a site except for a single cart.

## Collection Updates
Collections can be scheduled to automatically update. This is set in the collection **Properties** under the **Membership Rules** tab.
- Use incremental updates for this collection
    - This checkbox sets the collection to only add new members (does not remove devices that are no longer pulled in a query, etc).
- Schedule a full update on this collection
    - Clicking the **Schedule** button allows SCCM Administrators to set a schedule for a full evaluation update of a collection (this will both add new devices and remove devices). The SCCM Administrator can specify the frequency of collection updates. 
    - Note: Scheduling full updates too frequently on too many collections can bog down the SCCM server. It is good practice to have super critical collections update more frequently, and less critical collections update more leisurely.
