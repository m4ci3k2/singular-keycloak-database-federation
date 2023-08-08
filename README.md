# singular-keycloak-database-federation

## IMPORTANT !!

This repository was originaly created by OpenSingular at [singular-keycloak-databas-federation](https://github.com/opensingular/singular-keycloak-database-federationhttps:/) but the project has been dead since a few months ago. If you want me to take down this repository just let me know in a issue on this repo.

## Usage

Fully compatible with Singular Studio NOCODE. See https://www.studio.opensingular.com/

## Configuration

Keycloak User Federation Screen Shot

![Sample Screenshot](screen.png)

There is a new configuration that allows keycloak to remove a user entry from its local database (this option has no effect on the source database). It can be useful when you need to reload user data.
This option can be configured by the following switch:

![Sample Screenshot](deleteuser.png)

## Limitations

- Do not allow user information update, including password update
- Do not supports user roles our groups
- Keycloak must use a non-XA datasource

## Custom attributes

Just add a mapper to client mappers with the same name as the returned column alias in your queries.Use mapper type "User Attribute". See the example below:

![Sample Screenshot 2](screen2.png)

## Build

- mvn clean package

## Deployment

1) Copy every  `.jar` from dist/ folder  to  /providers folder under your keycloak installation root.
   - i.e, on a default keycloak setup, copy all  `.jar` files to <keycloak_root_dir>/providers
2) run :
   $ ./bin/kc.sh start-dev
   OR if you are using a production configuration:
   $ ./bin/kc.sh build
   $ ./bin/kc.sh start

## For futher information see:

- https://github.com/keycloak/keycloak/issues/9833
- https://www.keycloak.org/docs/latest/server_development/#packaging-and-deployment
