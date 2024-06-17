

# Desafio Dio - Adicionando Segurança em APIs na AWS com Amazon Cognito



####     Projeto ainda mais completo e abrangente com mais códigos para: 

##### Adicionando Segurança em APIs na AWS com Amazon Cognito



### **Como Adicionar :**

O Amazon Cognito é um serviço de gerenciamento de identidade e acesso que pode ser usado para adicionar segurança às APIs na AWS. Ele fornece recursos como autenticação, autorização e gerenciamento de usuários.

#### Para adicionar segurança em APIs na AWS com Amazon Cognito, você pode seguir os seguintes passos:



1. **Crie um pool de usuários do Cognito.**
2. **Adicione usuários ao pool de usuários.**
3. **Crie um grupo de usuários do Cognito.**
4. **Adicione usuários ao grupo de usuários.**
5. **Crie uma política de identidade do Cognito.**
6. **Adicione a política de identidade do Cognito à API Gateway.**

Depois de seguir esses passos, suas APIs serão protegidas pelo Amazon Cognito. Os usuários só poderão acessar as APIs se tiverem sido adicionados ao grupo de usuários correto e se tiverem uma política de identidade do Cognito válida.



#### **Códigos de exemplo**

#### **Criar um pool de usuários do Cognito**

plaintext

```plaintext
aws cognito-idp create-user-pool \
--pool-name my-user-pool \
--schema my-schema
```



#### **Adicionar usuários ao pool de usuários**

plaintext



```plaintext
aws cognito-idp admin-create-user \
--user-pool-id my-user-pool-id \
--username my-username \
--user-attributes Name=email,Value=my-email@example.com
```



#### **Criar um grupo de usuários do Cognito**

plaintext



```plaintext
aws cognito-idp create-group \
--group-name my-group-name \
--user-pool-id my-user-pool-id
```



#### **Adicionar usuários ao grupo de usuários**

plaintext



```plaintext
aws cognito-idp admin-add-user-to-group \
--user-pool-id my-user-pool-id \
--username my-username \
--group-name my-group-name
```



#### **Criar uma política de identidade do Cognito**

plaintext



```plaintext
aws cognito-identity create-identity-pool \
--identity-pool-name my-identity-pool-name \
--allow-unauthenticated-identities
```



#### **Adicionar a política de identidade do Cognito à API Gateway**

plaintext



```plaintext
aws apigateway update-authorizer \
--rest-api-id my-rest-api-id \
--authorizer-id my-authorizer-id \
--identity-source "method.request.header.Authorization" \
--authorizer-uri https://cognito-idp.us-east-1.amazonaws.com/my-user-pool-id/.well-known/jwks.json
```



#### *Explicações**

- **Pool de usuários do Cognito:** Um pool de usuários é um repositório de usuários que podem acessar seus aplicativos.
- **Grupo de usuários do Cognito:** Um grupo de usuários é uma coleção de usuários que compartilham permissões comuns.
- **Política de identidade do Cognito:** Uma política de identidade é um documento que define as permissões que os usuários têm para acessar seus recursos da AWS.
- **API Gateway:** O API Gateway é um serviço que permite que você crie e gerencie APIs.

Seguindo esses passos, você pode adicionar segurança às suas APIs na AWS usando o Amazon Cognito.

