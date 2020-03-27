## Authorization Code Flow
Below you can see one of the flows we are working on as part of the protocol, in this case it refers to the one on top of OpenId Authorization Code. For more details about this specification, please follow this [link](../auth_code/dtp-auth-code-00.html).

![Auth Code Flow](../auth_code/DiagramRFC.svg "Auth Code Flow")

In summary, this flow consists in 3 steps:

- RP sends request from backend with claims to be shared or verified. In return, a unique `request_uri` is obtained.
- RP redirects User to OP in the front-end passing the `request_uri`. User will authenticate and authorize (consent) the request, redirecting back to RP passing `authorization code`.
- RP exchanges the `code` with an `id_token`, which contains the response with the claims accepted by the User

To visualize the whole E2E, lets take the example of a fake company which allows small businesses offering temporal jobs to verified people. To verify people interested in taking the job, this company will validate birthdate, country of birth, address and name, and in addition to that, it will also ask for a telephone number and email address.

The picture above shows the screens presented by the OP to the user before returning back to the RP:

![Consent](../images/consent.png Consent")