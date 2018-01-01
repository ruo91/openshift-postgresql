# OpenShift - Image deploy template for PostgreSQL

1. Git Clone
```sh
# git clone https://github.com/ruo91/openshift-postgresql.git cd openshift-postgresql
```

# 2. Create Template
#### - Ephemeral
```sh
# oc create -n openshift -f postgresql-ephemeral-template.yml
```

#### - Persistent
```sh
# oc create -n openshift -f postgresql-persistent-template.yml
```

# 3. Deploy Pod
```sh
# oc new-app -n ybkim -p POSTGRESQL_VERSION=9.4 postgresql-ephemeral
```
``` --> Deploying template "openshift/postgresql-ephemeral" to project ybkim
     PostgreSQL (Ephemeral)
     ---------
     PostgreSQL database service, without persistent storage. For more information about using this template, including OpenShift considerations, see https://github.com/sclorg/postgresql-container
     WARNING: Any data stored will be lost upon pod destruction. Only use this template for testing
     The following service(s) have been created in your project: postgresql.
            Username: user741
            Password: Q1mRPbRGFu85rvi4
       Database Name: sampledb
      Connection URL: postgresql://postgresql:5432/
     For more information about using this template, including OpenShift considerations, see https://github.com/sclorg/postgresql-container
     * With parameters:
        * Memory Limit=512Mi
        * Namespace=openshift
        * Database Service Name=postgresql
        * PostgreSQL Connection Username=user741 # generated
        * PostgreSQL Connection Password=Q1mRPbRGFu85rvi4 # generated
        * PostgreSQL Database Name=sampledb
        * Version of PostgreSQL Image=9.4 --> Creating resources ...
    secret "postgresql" created
    service "postgresql" created
    deploymentconfig "postgresql" created --> Success
    Run 'oc status' to view your app.
```
