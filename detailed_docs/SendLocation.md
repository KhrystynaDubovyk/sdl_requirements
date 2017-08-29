## Use Case 1: SendLocation

**Main Flow:**

_Pre-conditions:_

a. HMI and SDL are started

b. appID is registered on SDL

_Steps:_

1. appID requests SendLocation with address, longtitudeDegrees, latitudeDegrees, deliveryMode and other parameters

_Expected:_

2. SDL checks if Navi interface is available on HMI
3. SDL checks if SendLocation is allowed by Policies
4. SDL checks if deliveryMode is allowed by Policies
5. SDL validates other parameters of RPC
6. SDL transfers the request with valid and allowed parameters to HMI
7. SDL receives response from HMI
8. SDL transfers response to mobile app

**Alternative flow 1:**

1.a.1. appID requests SendLocation **without** address and with longtitudeDegrees, latitudeDegrees, deliveryMode and other valid and allowed parameters

1.a.2. SDL transfers the requests to HMI

**Alternative flow 2:**

1.b.1. appID requests SendLocation **with** address, latitudeDegrees, deliveryMode, other parameters and without longtitudeDegrees

1.b.2. SDL responds "INVALID_DATA, success:false" to appID and doesn't transfer the request on HMI

**Alternative flow 3:**

1.c.1. appID requests SendLocation with address, longtitudeDegrees, deliveryMode, other valid and allowed parameters and **without** latitudeDegrees

1.c.2. SDL responds "INVALID_DATA, success:false" to appID and doesn't transfer the request on HMI

**Alternative flow 4:**

1.d.1. appID requests SendLocation **with** address, deliveryMode, other valid and allowed parameters and **without** latitudeDegrees and  longtitudeDegrees

1.d.2. SDL responds "INVALID_DATA, success:false" to appID and doesn't transfer the request on HMI

**Alternative flow 5:**

1.e.1. appID requests SendLocation **with deliveryMode**, other valid and allowed parameters and **without**  address, latitudeDegrees and  longtitudeDegrees

1.e.2. SDL responds "INVALID_DATA, success:false" to appID and doesn't transfer the request on HMI

**Alternative flow 5:**

1.f.1. appID requests SendLocation **without** deliveryMode and with other allowed and valid parameters 

1.f.2. SDL transfers the requests to HMI

**Exception 1:**

2.1.a Navi interface is not available on HMI

2.1.b SDL respponds with UNSUPPORTED_RESOURCE, success: false to mobile app

**Exception 2:**

3.1.a SendLocaction is not allowed by Policies

3.1.b. SDL responds DISALLOWED, success:false and doesn't transfer this request to HMI

**Exception 3:**

4.1.a deliveryMode is not allowed by Policies

4.1.b SDL cuts off deliveryMode parameter from application's request and if other parameters are valid, transfers request to HMI without deliverMode

4.1.c SDL transfers received response from HMI to mobile app with added info: "default value of deliveryMode will be used"

**Exception 4:**

5.1.a Non-mandatory parameter is invalid in SendLocation request from mobile app

5.1.b SDL cuts off invalid parameter and transfers request to HMI

**Exception 5:**

5.2.a Mandatory parameter is invalid in SendLocation request from mobile app

5.2.b SDL responds INVALID_DATA, success:false to mobile app without transferring this request to HMI

**Exception 6:**

5.3.a Some of requested parameters are not allowed by Policies

5.3.b SDL cuts off disallowed by Policies parameters and transfers request to HMI

5.3.c SDL transfers received result code from HMI to mobile app with info: "<param_1>, <param_2> parameters are disallowed by Policies"

**Exception 7:**

5.4.a Some of requested parameters are disallowed in Policies by user

5.4.b SDL cuts off disallowed by user parameters and transfers request to HMI

5.4.c SDL transfers received result code from HMI with info: "<param_1>, <param_2> are disallowed by user"

**Exception 8:**

5.5.a "parameters" field is omitted in Policy Table for SendLocation RPC

5.5.b SDL transfers request with all valid parameters to HMI

**Exception 9:**

5.6.a All requested paramters are disallowed by Policies

5.6.b SDL responds with DISALLOWED, success:false result code and info: "Requested parameters are disallowed by Policies"


> _[Requirement #24](https://github.com/smartdevicelink/sdl_requirements/issues/24) SendLocation to set a location on the head unit_