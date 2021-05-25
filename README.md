Ansible playbook used to secure the master/controlplane node in a kubernetes cluster.


# Important
The security of your server is your own job. This sets up and checks a few important things, but not all of them.

# Notes
- anonymous-auth is not set to false because if set, nodes cannot join the cluster.
- No Admission control plugins have been set
- Some checks have been left out since they may result in an issue with the deployment if they are included or are too custom

# Supported variables

~~~
check_cluster_role_bindings
~~~
Checks if there is only one cluster-admin role binding
Defaults to: `yes`.

~~~
fix_file_permissions
~~~
Fixes all the relevant file permissions to be less open
Defaults to: `yes`.

~~~
fix_k8s_components
~~~
Edits some k8s manifest files to fix security issues
Defaults to: `yes`.

~~~
check_roles_have_wildcard_all
~~~
Checks if there are any wildcards in roles
Defaults to: `yes`.

~~~
check_default_namespace_empty
~~~
Checks if the default namespace has anything besides the kubernetes service
Defaults to: `yes`.
