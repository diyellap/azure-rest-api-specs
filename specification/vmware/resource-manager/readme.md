# VMware Solution

> see https://aka.ms/autorest

This is the AutoRest configuration file for VMware Solution.

## Getting Started
To build the SDK for VMware Solution, simply [Install AutoRest](https://aka.ms/autorest/install) and in this folder, run:

> `autorest`

To see additional help and options, run:

> `autorest --help`
---

## Configuration

### Basic Information
These are the global settings for the VMware Solution API.

``` yaml
openapi-type: arm
tag: package-2022-05-01
```

### Tag: package-2022-05-01

These settings apply only when `--tag=package-2022-05-01` is specified on the command line.

``` yaml $(tag) == 'package-2022-05-01'
input-file:
- Microsoft.AVS/stable/2022-05-01/vmware.json
```

### Tag: package-2021-12-01

These settings apply only when `--tag=package-2021-12-01` is specified on the command line.

``` yaml $(tag) == 'package-2021-12-01'
input-file:
- Microsoft.AVS/stable/2021-12-01/vmware.json
```

### Tag: package-2021-06-01

These settings apply only when `--tag=package-2021-06-01` is specified on the command line.

``` yaml $(tag) == 'package-2021-06-01'
input-file:
- Microsoft.AVS/stable/2021-06-01/vmware.json
```

### Tag: package-2021-01-01-preview

These settings apply only when `--tag=package-2021-01-01-preview` is specified on the command line.

``` yaml $(tag) == 'package-2021-01-01-preview'
input-file:
- Microsoft.AVS/preview/2021-01-01-preview/vmware.json
```

### Tag: package-2020-07-17-preview

These settings apply only when `--tag=package-2020-07-17-preview` is specified on the command line.

``` yaml $(tag) == 'package-2020-07-17-preview'
input-file:
- Microsoft.AVS/preview/2020-07-17-preview/vmware.json
```

### Tag: package-2020-03-20

These settings apply only when `--tag=package-2020-03-20` is specified on the command line.

``` yaml $(tag) == 'package-2020-03-20'
input-file:
- Microsoft.AVS/stable/2020-03-20/vmware.json
```

---
# Code Generation

## Swagger to SDK

This section describes what SDK should be generated by the automatic system.
This is not used by Autorest itself.

``` yaml $(swagger-to-sdk)
swagger-to-sdk:
  - repo: azure-sdk-for-js
  - repo: azure-sdk-for-python-track2
  - repo: azure-sdk-for-net
  - repo: azure-sdk-for-go
  - repo: azure-sdk-for-java
  - repo: azure-resource-manager-schemas
  - repo: azure-powershell
```

## Suppression

### AutoRest v2 Suppressions
``` yaml
directive:
  - suppress: pathresourceprovidernamepascalcase
    reason: Microsoft.AVS was chosen over Microsoft.AzureVMwareSolution
    from: vmware.json

  - suppress: TrackedResourceListByImmediateParent
    reason: list by immediate parent operations are defined
    from: vmware.json
    
  - suppress: TrackedResourceListByResourceGroup
    reason: the PrivateClouds_List operation is by resource group
    from: vmware.json

  - suppress: EnumInsteadOfBoolean
    reason: standard property for Operation
    from: vmware.json
    where: $.definitions.Operation.properties.isDataAction
    
  - suppress: EnumInsteadOfBoolean
    reason: standard property for MetricSpecification
    from: vmware.json
    where: $.definitions.MetricSpecification.properties.fillGapWithZero

  - suppress: AvoidNestedProperties
    reason: x-ms-client-flatten not needed for Operation
    from: vmware.json
    where: $.definitions.Operation.properties.properties

  - suppress: RequiredReadOnlySystemData
    reason: systemData is not in this API version
    from: vmware.json

  - suppress: EnumInsteadOfBoolean
    reason: standard property defined by Geneva Metrics
    from: vmware.json
    where: $.definitions.MetricDimension.properties.toBeExportedForShoebox

  - suppress: ParametersOrder
    reason: Breaking change to update the parameters order
    from: vmware.json
    where:
      - $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.AVS/privateClouds/{privateCloudName}/workloadNetworks/default/dhcpConfigurations/{dhcpId}"].get
      - $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.AVS/privateClouds/{privateCloudName}/workloadNetworks/default/portMirroringProfiles/{portMirroringId}"].delete
      - $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.AVS/privateClouds/{privateCloudName}/workloadNetworks/default/vmGroups/{vmGroupId}"].delete
      - $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.AVS/privateClouds/{privateCloudName}/workloadNetworks/default/dnsServices/{dnsServiceId}"].delete
      - $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.AVS/privateClouds/{privateCloudName}/workloadNetworks/default/dnsZones/{dnsZoneId}"].delete
      - $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.AVS/privateClouds/{privateCloudName}/workloadNetworks/default/publicIPs/{publicIPId}"].delete
```

### AutoRest v3 Suppressions
``` yaml
suppressions:
    
  - code: pathresourceprovidernamepascalcase
    reason: Microsoft.AVS was chosen over Microsoft.AzureVMwareSolution
    from: vmware.json

  - code: ParametersOrder
    reason: Breaking change to update the parameters order
    from: vmware.json
    where:
      - $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.AVS/privateClouds/{privateCloudName}/workloadNetworks/default/dhcpConfigurations/{dhcpId}"].get
      - $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.AVS/privateClouds/{privateCloudName}/workloadNetworks/default/portMirroringProfiles/{portMirroringId}"].delete
      - $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.AVS/privateClouds/{privateCloudName}/workloadNetworks/default/vmGroups/{vmGroupId}"].delete
      - $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.AVS/privateClouds/{privateCloudName}/workloadNetworks/default/dnsServices/{dnsServiceId}"].delete
      - $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.AVS/privateClouds/{privateCloudName}/workloadNetworks/default/dnsZones/{dnsZoneId}"].delete
      - $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.AVS/privateClouds/{privateCloudName}/workloadNetworks/default/publicIPs/{publicIPId}"].delete
    
  - code: ConsistentPatchProperties
    reason: The properties are consistent for the discriminator hierarchy.
    from: vmware.json
    # where:
    #   - $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.AVS/privateClouds/{privateCloudName}/clusters/{clusterName}/placementPolicies/{placementPolicyName}"].patch
    #   - $.definitions.PlacementPolicyUpdate.properties.vmMembers
    #   - $.definitions.PlacementPolicyUpdate.properties.hostMembers
    #   - $.definitions.PlacementPolicyUpdate.properties.affinityStrength
    #   - $.definitions.PlacementPolicyUpdate.properties.azureHybridBenefitType

  - code: DefinitionsPropertiesNamesCamelCase
    reason: Breaking change to update existing property names
    from: vmware.json
    where:
      - $.definitions.Circuit.properties.expressRouteID
      - $.definitions.Circuit.properties.expressRoutePrivatePeeringID
      - $.definitions.IdentitySource.properties.baseUserDN
      - $.definitions.IdentitySource.properties.baseGroupDN
      - $.definitions.WorkloadNetworkPublicIPProperties.properties.numberOfPublicIPs
      - $.definitions.WorkloadNetworkPublicIPProperties.properties.publicIPBlock
      - $.definitions.WorkloadNetworkPublicIPProperties.properties.numberOfPublicIPs

  - code: ArmResourcePropertiesBag
    reason: Breaking change to update existing property names
    from: vmware.json
    where:
      - $.definitions.PlacementPolicy

  - code: DeleteOperationAsyncResponseValidation
    reason: x-ms-long-running-operation-options does not need to be set if you follow ARM guidelines
    # https://azure.github.io/autorest/extensions/#x-ms-long-running-operation-options
    from: vmware.json

  - code: PatchSkuProperty
    reason: sku can not be updated
    from: vmware.json
    # where:
    #   - $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.AVS/privateClouds/{privateCloudName}"].patch
    #   - $.definitions.PrivateCloudUpdate
    #   - $.definitions.ClusterUpdate

  - code: LroPatch202
    reason: Breaking change to add response
    from: vmware.json
    # where:
    #   - $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.AVS/privateClouds/{privateCloudName}"].patch
    #   - $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.AVS/privateClouds/{privateCloudName}/clusters/{clusterName}"].patch

  - code: UnSupportedPatchProperties
    reason: Breaking change to remove name or type properties
    from: vmware.json
    # where: 
    #   - $ $.paths["/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.AVS/privateClouds/{privateCloudName}/workloadNetworks/default/segments/{segmentId}"].patch

  - code: XmsLongRunningOperationOptions
    reason: This option is designed for cases where the server does NOT follow ARM guidelines
    # https://azure.github.io/autorest/extensions/#x-ms-long-running-operation-options
    from: vmware.json

  # just warnings
  # - code: IgnoredPropertyNextToRef
  # - code: LroLocationHeader
  #   from: vmware.json
```

## TypeScript

See configuration in [readme.typescript.md](./readme.typescript.md)

## Python

See configuration in [readme.python.md](./readme.python.md)

## C#

See configuration in [readme.csharp.md](./readme.csharp.md)

## Go

See configuration in [readme.go.md](./readme.go.md)

## Java

See configuration in [readme.java.md](./readme.java.md)



