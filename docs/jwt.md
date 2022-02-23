## How JWT Works
JWTs differ from other web tokens in that they contain a set of claims. 
Claims are used to transmit information between two parties.
What these claims are depends on the use case at hand. 
For example, a claim may assert who issued the token, how long it is valid for, 
or what permissions the client has been granted.

A JWT is a string made up of three parts, separated by dots (.), and serialized using base64. 
In the most common serialization format, compact serialization,
the JWT looks something like this: xxxxx.yyyyy.zzzzz.

Once decoded, you will get two JSON strings:

 - The header and the payload.
 - The signature.

The JOSE (JSON Object Signing and Encryption) header contains the type of token
— JWT in this case — and the signing algorithm.

The payload contains the claims. This is displayed as a JSON string, usually containing 
no more than a dozen fields to keep the JWT compact. This information is typically used by 
the server to verify that the user has permission to perform the action they are requesting.

There are no mandatory claims for a JWT, but overlaying standards may make claims mandatory. 
For example, when using JWT as bearer access token under OAuth2.0, iss, sub, aud, and exp must be present. 
Some are more common than others.

The signature ensures that the token hasn’t been altered. 
The party that creates the JWT signs the header and payload with a secret that is known to both the issuer
and receiver, or with a private key known only to the sender. 
When the token is used, the receiving party verifies that the header and payload match the signature.

## JWT Example: OAuth Bearer Tokens
A common way to use JWTs is as OAuth bearer tokens. In this example, an authorization server creates a JWT 
at the request of a client and signs it so that it cannot be altered by any other party.
The client will then send this JWT with its request to a REST API. 
The REST API will verify that the JWT’s signature matches its payload and header to determine 
that the JWT is valid. When the REST API has verified the JWT, it can use the claims 
to either grant or deny the client’s request.

In simpler terms, you can think of a JWT bearer token as an identity badge to get into a secured building. 
The badge comes with special permissions (the claims); that is, it may grant access 
to only select areas of the building. The authorization server in this analogy 
is the reception desk — or the issuer of the badge. And to verify that the badge is valid, 
the company logo is printed on it, similar to the signature of the JWT. 
If the badge holder attempts to access a restricted area, the permissions on the badge determine 
whether or not they can access the area, similar to the claims in a JWT.

## Why Use JWT?
In short, JWTs are used as a secure way to authenticate users and share information.

Typically, a private key, or secret, is used by the issuer to sign the JWT. 
The receiver of the JWT will verify the signature to ensure that the token hasn’t been altered 
after it was signed by the issuer. It is difficult for unauthenticated sources to guess the 
signing key and attempt to change the claims within the JWT.

Not all signing algorithms are created equal though. For example, some signing
algorithms use a secret value that is shared between the issuer and the party
that verifies the JWT. Other algorithms use a public and private key. 
The private key is known only to the issuer, while the public key can be widely distributed. 
The public key can be used to verify the signature, but only the private key can be used to create
the signature. This is more secure than a shared secret because the private key only
needs to exist in one place.

Because of this, the server does not need to keep a database with the information
needed to identify the user. For developers, this is great news — the server that issues the JWT
and the server that validates it do not have to be the same. 
