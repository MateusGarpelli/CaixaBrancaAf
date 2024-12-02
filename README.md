# Caixa-Branca

![image](https://github.com/user-attachments/assets/57916b6a-3cb1-4ada-b6e3-c168f6d00588)

<h2>Estrutura de Nós e Caminhos</h2>

<h3>Nós</h3>

<ul>
    <li>
        <strong>Nodo 1 (Início do Método Conexão)</strong>
        <pre>
public class User {
    public Connection conectarBD() {
        Connection conn = null;
        </pre>
    </li>
    <li>
        <strong>Nodo 2 (Carregar Driver e Conectar ao Banco de Dados)</strong>
        <pre>
try {
    Class.forName("com.mysql.cj.jdbc.Driver").newInstance();
    String url = "jdbc:mysql://127.0.0.1/teste?user=root&password=1234";
    conn = DriverManager.getConnection(url);
        </pre>
    </li>
    <li>
        <strong>Nodo 3 (Tratamento de Exceção)</strong>
        <pre>
} catch (Exception e) {
}
        </pre>
    </li>
    <li>
        <strong>Nodo 4 (Retorno da Conexão)</strong>
        <pre>
return conn;
        </pre>
    </li>
    <li>
        <strong>Nodo 5 (Atributos e Método de Verificação)</strong>
        <pre>
public String nome = "";

public boolean result = false;

public boolean verificarUsuario(String login, String senha) {

    String sql = "";
    Connection conn = conectarBD();

    // INSTRUÇÃO SQL
    sql = "select nome from usuarios ";
    sql += "where login = '" + login + "' ";
    sql += "and senha = '" + senha + "';";
        </pre>
    </li>
    <li>
        <strong>Nodo 6 (Executar Consulta SQL)</strong>
        <pre>
try {
    Statement st = conn.createStatement();
    ResultSet rs = st.executeQuery(sql);
    if (rs.next()) {
        result = true;
        nome = rs.getString("nome");
    }
        </pre>
    </li>
    <li>
        <strong>Nodo 7 (Tratamento de Exceção)</strong>
        <pre>
} catch (Exception e) {
}
        </pre>
    </li>
    <li>
        <strong>Nodo 8 (Validação de Resultados)</strong>
        <pre>
if (rs.next()) {
    result = true;
    nome = rs.getString("nome");
}
        </pre>
    </li>
    <li>
        <strong>Nodo 9 (Retorno do Resultado da Verificação)</strong>
        <pre>
return result;
        </pre>
    </li>
</ul>

<h3>Caminhos e Conta dos Caminhos</h3>

<ul>
    <li><strong>C1</strong> = Nodo 1, Nodo 2, Nodo 4, Nodo 5, Nodo 6, Nodo 8, Nodo 9</li>
    <li><strong>C2</strong> = Nodo 1, Nodo 3</li>
    <li><strong>C3</strong> = Nodo 1, Nodo 2, Nodo 4, Nodo 5, Nodo 7</li>
</ul>

<h3>Complexidade Ciclomática</h3>

<p>
    A fórmula para calcular a complexidade ciclomática é:
</p>

<pre>
V(G) = E - N + 2
</pre>

<ul>
    <li>E = 9 (número de arestas)</li>
    <li>N = 8 (número de nós)</li>
</ul>

<p>
    Aplicando a fórmula:
</p>

<pre>
V(G) = 9 - 8 + 2
V(G) = 3
</pre>
