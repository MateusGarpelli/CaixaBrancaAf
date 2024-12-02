<h1>Caixa-Branca</h1>
    <h2>Descrição</h2>
    <p>Este projeto consiste em duas classes principais:</p>
    <ul>
        <li><strong>User.java</strong>: Contém métodos para estabelecer conexão com o banco de dados e verificar se um usuário existe.</li>
        <li><strong>Teste.java</strong>: Classe de teste para verificar o funcionamento dos métodos da classe <code>User</code>.</li>
    </ul>
    <h2>Como Executar</h2>
    <h3>Passo 1: Criar o Banco de Dados</h3>
    <p>Execute os seguintes comandos SQL para configurar o banco de dados:</p>
    <h4>Criação do Banco de Dados</h4>
    <pre>
CREATE DATABASE teste;
    </pre>
    <h4>Criação da Tabela <code>usuarios</code></h4>
    <pre>
CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    login VARCHAR(50) NOT NULL,
    senha VARCHAR(50) NOT NULL,
    nome VARCHAR(100) NOT NULL
);
    </pre>
    <h3>Passo 2: Inserir Dados no Banco de Dados</h3>
    <p>Adicione os seguintes dados ao banco de dados:</p>
    <pre>
INSERT INTO usuarios (login, senha, nome) VALUES ('Zhefiroth', '1234', 'Matheus');
    </pre>
    <h3>Passo 3: Configurar a URL de Conexão</h3>
    <p>Atualize a URL no código para apontar para o seu banco de dados:</p>
    <pre>
"jdbc:mysql://127.0.0.1/Nome_do_seu_Banco_de_Dados?user=Seu_usuario_do_MYSQL&password=Sua_senha"
    </pre>
    <h3>Passo 4: Baixar o Driver MySQL</h3>
    <p>Faça o download do driver JDBC MySQL no site:</p>
    <a href="https://dev.mysql.com/downloads/connector/j/" target="_blank">https://dev.mysql.com/downloads/connector/j/</a>
    <p>Selecione a opção <strong>Platform Independent</strong> e faça o download do arquivo <strong>Platform Independent (Architecture Independent), ZIP Archive</strong>.</p>
    <p>Extraia o arquivo ZIP, localize o JAR <code>mysql-connector-j-9.1.0.jar</code> e adicione-o ao seu projeto.</p>
    <h3>Passo 5: Executar o Projeto</h3>
    <p>Após seguir os passos acima, o projeto estará funcionando corretamente.</p>
