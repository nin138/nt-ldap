localhost:8080 

Login DN: cn=root,dc=hal,dc=ac,dc=jp
Password: password
```
$ docker-compose up -d
$ docker-compose exec ldap sh -c "\
ldapadd -f /ldif/ou/users.ldif -x -D "cn=admin,dc=hal,dc=ac,dc=jp" -w admin && \
ldapadd -f /ldif/ou/computers.ldif -x -D "cn=admin,dc=hal,dc=ac,dc=jp" -w admin && \
ldapadd -f /ldif/ou/groups.ldif -x -D "cn=admin,dc=hal,dc=ac,dc=jp" -w admin && \
ldapadd -f /ldif/cn/user1.ldif -x -D "cn=admin,dc=hal,dc=ac,dc=jp" -w admin && \
ldapadd -f /ldif/cn/com1.ldif -x -D "cn=admin,dc=hal,dc=ac,dc=jp" -w admin && \
ldapadd -f /ldif/cn/g1.ldif -x -D "cn=admin,dc=hal,dc=ac,dc=jp" -w admin && \
ldapmodify -f /ldif/root.ldif -x -D "cn=admin,dc=hal,dc=ac,dc=jp" -w admin"
```
