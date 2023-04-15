kubectl
create 
secret
generic
<secret_name>
--from-literal=<key>=<value>

--from-literal is used to create a secret from a literal value, rather than a file.

generic is used unless storing tls or docker-registry stuff.

# The command I ended up using:
```bash
kubectl create secret generic pgpassword --from-literal=PGPASSWORD=magicalunicorn
```