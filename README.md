## SecureX Orchestrator Atomic Actions for Cisco Defense Orchestrator (CDO)

[![published](https://static.production.devnetcloud.com/codeexchange/assets/images/devnet-published.svg)](https://developer.cisco.com/codeexchange/github/repo/ciscomanagedservices/sxo-cdo)

NOTE: Some atomic actions in this repository make use of CDO's REST API & not the official GraphQL-based Public API. Whilst the atomics that use the REST API aren't an officially supported methodology to programmatically interact with CDO, these endpoints are the same as what the CDO GUI uses and therefore, considered stable and suitable for use, especially in cases where the GraphQL-based Public API may not support certain methods.

Additional Resources: 

- CDO Docs: https://docs.defenseorchestrator.com/
- CDO Public API Docs: https://edge.staging.cdo.cisco.com/api-explorer/docs/

### In this repository, you'll find the following atomics:

#### 1. [Command Runner](/CDO-CommandRunner__definition_workflow_01OE01E2YS1GN1A87j4O3smtRPRCD89FhjK)

> **Purpose:** This atomic action makes use of CDO's REST API to run a CLI command on an ASA

Steps to use:
1. Create a target for the CDO REST API: https://www.defenseorchestrator.com/aegis/rest/v1/
2. Input CDO API Token to this workflow
3. Supply the ASA's UID and the command to run  as inputs
4. The output of this atomic action is the CLI response of the command as seen on the device

---

#### 2. [Create New ACL](/CDO-CreateNewACL__definition_workflow_01O8Z7962JCXE0QUrWy4FpOGFZquIm43kHr)

> **Purpose:** This atomic action makes use of CDO's REST API to create an Access List on CDO with an associated Network Object Group

Steps to use:
1. Create a target for the CDO REST API: https://www.defenseorchestrator.com/aegis/rest/v1/
2. Input CDO API Token to this workflow
3. Supply Input Variables (all variables have descriptions in-line)
4. Tweak "Parse Response" JSONPath Query to pick out an attribute (by default, UID of the Access Group created)
5. The output of this atomic action is the UID of the Access Group created

---

#### 3. [Delete Objects](/CDO-DeleteObjects__definition_workflow_01O42SX1E88YV3h5f4UKjH89MNIRmQBvj8t)

> **Purpose:** This atomic action makes use of CDO's REST API to delete unused Object Groups on CDO by their UIDs

Steps to use:
1. Create a target for the CDO REST API: https://www.defenseorchestrator.com/aegis/rest/v1/
2. Input CDO API Token to this workflow
3. Supply a comma-separated list of UIDs of objects to delete - ensure these objects are not already associated with any devices
4. If this atomic action runs successfully, a successful response was received from CDO

---

#### 4. [Deploy Job By Device](/CDO-DeplyJobByDevice__definition_workflow_01O42UBNKGXN31EqF51dp9qheqplTEMTdd6)

> **Purpose:** This atomic action makes use of CDO's REST API to launch a deployment job on CDO

Steps to use:
1. Create a target for the CDO REST API: https://www.defenseorchestrator.com/aegis/rest/v1/
2. Input CDO API Token to this workflow
3. Supply the device UID of a device with one or more staged changes
4. The output of this atomic action is the UID of the CDO job launched

---

#### 5. [Generic GraphQL](/CDO-GenericGraphQL__definition_workflow_01O41JK2236CY7QVz8OBWeB66FzpdgyPMt9)

> **Purpose:** This atomic action makes it possible to use GraphQL with SXO's Web Service Adapter

Steps to use:
1. Create a target https://edge.us.cdo.cisco.com
2. Input CDO API Token to this workflow
3. Supply GraphQL query from API docs

---

#### 6. [Get Object Group By Name](/CDO-GetObjectGroupByName__definition_workflow_01O6IPKZS51QX3DVF1ru9bVbQPjUrIfD3fF)

> **Purpose:** This atomic action makes it possible to use GraphQL to retrieve an Object Group's UID given it's name with SXO's Web Service Adapter

Steps to use:
1. Create a target https://edge.us.cdo.cisco.com
2. Input CDO API Token to this workflow
3. Supply the name of the object group to search for (by default, only the first match is returned)
4. The output of this atomic action is the UID of the object group

---

#### 7. [Monitor Jobs](/CDO-MonitorJobs__definition_workflow_01O5037A0BIRH6MFeU1CH8LlcbAdwYiuwzN)

> **Purpose:** This atomic action makes use of CDO's REST API to monitor a deployment job on CDO

Steps to use:
1. Create a target for the CDO REST API: https://www.defenseorchestrator.com/aegis/rest/v1/
2. Input CDO API Token to this workflow
3. Supply the job UID as input (optional)
4. The output of this atomic action is the status of a job on CDO. If no job UID is supplied, the output is the overall status of all jobs on CDO.

---

#### 8. [Create New Object Group](/CDO-NewObjectGroup__definition_workflow_01O42NVHDGV3C76X21klV5fKoOeioE4i72B)

> **Purpose:** This atomic action makes it possible to use GraphQL to create a new object group on CDO with SXO's Web Service Adapter

Steps to use:
1. Create a target https://edge.us.cdo.cisco.com
2. Input CDO API Token
3. Supply input variables
4. Tweak "Parse Response" JSONPath Query to pick out an attribute (by default, UID)
5. The output of this atomic action is the UID of the object group created

---

#### 9. [Create New Service Object](/CDO-NewServiceObject__definition_workflow_01O7PRKHLAVEG0ZlODoGdPH324Ct6GKlqoT)

> **Purpose:** This atomic action makes use of CDO's REST API to create a new service object on CDO

Steps to use:
1. Create a target for the CDO REST API: https://www.defenseorchestrator.com/aegis/rest/v1/
2. Input CDO API Token to this workflow
3. Supply the device UID of a device with one or more staged changes
4. The output of this atomic action is the UID of the CDO job launched

---

#### 10. [Query Devices](/CDO-QueryDevicesGQL__definition_workflow_01O41U1G6U6E75n0jsxhpgcYfiLsOojycJH)

> **Purpose:** This atomic action makes it possible to use GraphQL to query devices by either name, IP address, serial, or interfaces with SXO's Web Service Adapter

Steps to use:
1. Create a target https://edge.us.cdo.cisco.com
2. Input CDO API Token
3. Supply Search Term
4. Tweak "Parse Response" JSONPath Query to pick out an attribute (by default, UID)
5. The Output of this workflow is a list of Device UIDs (could be one or more based on search term)

---

#### 11. [Terminate VPN Sessions](/CDO-TerminateVPNSessions__definition_workflow_01OE527TJW9VY25isdahnMsvAjvZZrIztQF)

> **Purpose:** This atomic action makes use of CDO's REST API to terminate VPN sessions across all devices given a User's ID

Steps to use:
1. Create a target for the CDO REST API: https://www.defenseorchestrator.com/aegis/rest/v1/
2. Input CDO API Token to this workflow
3. Supply the User's ID input
4. Successful execution of this atomic action indicates successful termination of VPN sessions for the given User ID

---

#### 12. [Update Object Group via GraphQL](/CDO-UpdateObjectGroupGQL__definition_workflow_01O6I9XWV8AUZ6BN6xwoDkkq9OiZqGvApyZ)

> **Purpose:** This atomic action makes it possible to use GraphQL to update an object group on CDO with SXO's Web Service Adapter.

Steps to use:
1. Create a target https://edge.us.cdo.cisco.com
2. Input CDO API Token
3. Supply input variables
4. Tweak "Parse Response" JSONPath Query to pick out an attribute (by default, UID)
5. The output of this atomic action is a comma-separated string of UIDs of all affected devices that are mapped to the updated object group

---

#### 13. [Update Object Group via REST](/CDO-UpdateObjectGroupREST__definition_workflow_01O6IBHXS1KLH6f1QqEjInFyOYKuHbpLnRl)

> **Purpose:** This atomic action makes use of CDO's REST API to update an existing object group on CDO. Use only in case there are issues with updating the object group via the GraphQL atomic. 

NOTE: This atomic will replace/overwrite all parameters. If you wish to append to existing configuration, you must include existing configuration in your input to this atomic.

Steps to use:
1. Create a target for the CDO REST API: https://www.defenseorchestrator.com/aegis/rest/v1/
2. Input CDO API Token to this workflow
3. Supply the device UID of a device with one or more staged changes
4. The output of this atomic action is the UID of the CDO job launched

---

Contributors:

1. Aman Sardana (amasarda@cisco.com)
2. Anant Nambiar (ananambi@cisco.com)

Cisco CX Managed Services - Operate, May 2021
