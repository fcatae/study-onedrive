# study-onedrive

## Overview

https://docs.microsoft.com/en-us/graph/onedrive-concept-overview

## App Registration

https://apps.dev.microsoft.com/?referrer=https%3A%2F%2Fdev.onedrive.com

- Create an application

## Authorization

https://docs.microsoft.com/en-us/onedrive/developer/rest-api/getting-started/authentication?view=odsp-graph-online

- Scopes: (files.read offline_access)
https://docs.microsoft.com/en-us/onedrive/developer/rest-api/getting-started/graph-oauth?view=odsp-graph-online
- Onedrive scopes: (onedrive.readwrite offline_access)
https://docs.microsoft.com/en-us/onedrive/developer/rest-api/getting-started/msa-oauth?view=odsp-graph-online

(implicit)
```
GET https://login.live.com/oauth20_authorize.srf
    ?client_id={client_id}
    &scope={scope}
    &response_type=token
    &redirect_uri={redirect_uri}
```

(auth code)
```
GET https://login.live.com/oauth20_authorize.srf
    ?client_id={client_id}
    &scope={scope}
    &response_type=code
    &redirect_uri={redirect_uri}
```

token endpoint
```
POST https://login.live.com/oauth20_token.srf
Content-Type: application/x-www-form-urlencoded

client_id={client_id}&redirect_uri={redirect_uri}&client_secret={client_secret}
&code={code}&grant_type=authorization_code
```

## Endpoint differences

Authorize
https://login.live.com/oauth20_authorize.srf
https://login.microsoftonline.com/common/oauth2/v2.0/authorize

Token
https://login.live.com/oauth20_token.srf
https://login.microsoftonline.com/common/oauth2/v2.0/token


###
GET /me/drives

Custom Metadata
https://docs.microsoft.com/en-us/onedrive/developer/rest-api/concepts/custom-metadata-facets?view=odsp-graph-online
