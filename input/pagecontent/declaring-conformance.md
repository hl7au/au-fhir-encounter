TBD


### FHIR Server CapabilityStatement

Servers that implement support for AU Encounter Record Summary profiles, declare conformance to each profile by hosting a [CapabilityStatement](http://hl7.org/fhir/capabilitystatement.html) resource at [server-base-url]/metadata that is available to both authenticated and unauthenticated clients. The capability statement declares support for a resource as either a base profile using [CapabilityStatement.rest.resource.profile](http://hl7.org/fhir/capabilitystatement-definitions.html#CapabilityStatement.rest.resource.profile) or supported profile using [CapabilityStatement.rest.resource.supportedProfile](http://hl7.org/fhir/capabilitystatement-definitions.html#CapabilityStatement.rest.resource.supportedProfile).

Example: CapabilityStatement resource for a server supporting the AU Encounter Record Composition profile as a system-wide profile that is applied across all instances of the Patient resource:

    ```
    {
      "resourceType": "CapabilityStatement",
      ...
      "rest": [
        {
          "mode": "server",
        ...
            "resource": [
              ...
              {
                "type": "Composition",
                "profile": "http://hl7.org.au/fhir/encounter/StructureDefinition/au-encounter-composition",
                ...
              }
            ]
        }
      ] 
    }
    ```

Example: CapabilityStatement resource for a server supporting the AU Encounter Record Composition profile as a profile for supported use cases provided by the server:

    ```
    {
      "resourceType": "CapabilityStatement",
      ...
      "rest": [
        {
          "mode": "server",
        ...
            "resource": [
              ...
              {
                "type": "Composition",
                "supportedProfile": [
                  "http://hl7.org.au/fhir/encounter/StructureDefinition/au-encounter-composition"
                ],
                ...
              }
            ]
        }
      ] 
    }
    ```