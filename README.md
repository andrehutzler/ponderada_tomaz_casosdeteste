# ponderada_tomaz_casosdeteste
atividade ponderada:

# Caso de Teste: Edição de Estimativa de Entrega no Sistema de Gerenciamento de Lojas

## PREPARAÇÃO:
1. Certificar-se de que o banco de dados MySQL no AWS RDS está configurado corretamente e conectado ao backend da aplicação.
2. Criar a tabela `stores` no banco de dados, utilizando a seguinte query:
    ```sql
    CREATE TABLE stores (
        id INT AUTO_INCREMENT PRIMARY KEY,
        initialZipcode VARCHAR(10),
        finalZipcode VARCHAR(10),
        estimatedDays INT
    );
    ```
3. Inserir os seguintes registros na tabela `stores`:
    ```sql
    INSERT INTO stores (initialZipcode, finalZipcode, estimatedDays) 
    VALUES 
    ('06470-000', '88808-000', 30),
    ('06470-890', '88899-000', 20);
    ```

## CONFIGURAÇÃO INICIAL:
1. Acessar a interface web do sistema de gerenciamento de inventário, hospedado no AWS S3.
2. Verificar que o sistema está conectado corretamente ao banco de dados MySQL no AWS RDS.
3. Navegar até a seção “Gerenciar Lojas”, onde é possível visualizar as lojas cadastradas e seus respectivos CEPs e estimativa de dias de entrega.

## PASSOS PARA A EXECUÇÃO:
1. Na página de "Gerenciar Lojas", localizar a loja com o **CEP inicial "06470-000"** e **CEP final "88808-000"**.
2. Clicar no botão "Editar" ao lado dessa loja.
3. No formulário de edição, alterar o campo "Dias Estimados" de **30 para 25 dias**.
4. Clicar no botão "Salvar" para confirmar a alteração.
5. Após salvar, clicar no botão "Exibir Dados" para visualizar todas as lojas cadastradas e confirmar as alterações.
6. Verificar na lista de lojas se a loja com **CEP inicial "06470-000"** e **CEP final "88808-000"** agora exibe **25 dias** como estimativa de entrega.

## RESULTADOS ESPERADOS:
- O sistema deve exibir uma mensagem de confirmação: **"Dados atualizados com sucesso."**
- Na tela de exibição de dados, a loja com **CEP inicial "06470-000"** e **CEP final "88808-000"** deve apresentar **25 dias** como a nova estimativa de entrega.
- No banco de dados, o campo `estimatedDays` da loja correspondente deve ter sido atualizado de **30 para 25**.
