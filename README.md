# Prepare nodes before running tests

<b>NodeManager</b> class can be used launching a specified number of nodes in a given timeout period. 
Also you can get total, free and busy node counts using <b>NodeManager</b> .

### Usage:

* For launching a specified number of nodes in a given timeout period.

```
      String hubUrl="https://...gridlastic.com/';
      String gridUsername=....;
      String gridAccessKey=...;
      int timeoutInSeconds=600;//10 minutes
      NodeManager nodeManager = new NodeManager(huburl, gridUsername, gridAccessKey);
      int freeNodesLaunched = nodeManager.launchNodes(browserName, browserVersion, platformName, desiredNodeCount, acceptableNodeCount, timeoutInSeconds);
               
```

* Get node counts

```
   int nodeCount = nodeManager.getNodeCount(browserName, browserVersion, platformName);
   int freeNodeCount = nodeManager.getFreeNodeCount(browserName, browserVersion, platformName);
   int busyNodeCount = nodeManager.getBusyNodeCount(browserName, browserVersion, platformName);  
```

### Maven dependency

Add below dependency into your project

```
   <dependency>
      <groupId>com.gridlastic</groupId>
      <artifactId>nodeManager</artifactId>
      <version>1.0</version>
   </dependency> 
```
### Internals

You can reach specs of node api from <b>https://<HUB_URL>/api/v1/openapi.json</b> or <b>https://<HUB_URL>/api/v1/openapi.yaml</b>.
You can generate api clients using [open api generator](https://github.com/OpenAPITools/openapi-generator)

####Sample Usage:
```
openapi-generator generate -i https://<HUB_URL>/api/v1/openapi.json -g -a Authorization:"Basic encoded-user-password" -o outputdir java
```