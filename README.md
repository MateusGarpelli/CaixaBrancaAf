# Caixa-Branca

Possíveis Erros e Melhorias
1. Classe do Driver MySQL
Erro:
Class.forName("com.mysql.Driver.Manager").newInstance();

Correção:
Class.forName("com.mysql.cj.jdbc.Driver").newInstance();
Descrição:
A classe especificada para o driver MySQL está incorreta. A classe correta é com.mysql.cj.jdbc.Driver.

2. String de Conexão
Erro:
String url = "jdbc:mysql://127.0.0.1/test?user=lopes&password=123";

Correção:
Evitar armazenar credenciais diretamente no código.

Descrição:
Armazenar credenciais de banco de dados diretamente no código pode levar a problemas de segurança. Recomenda-se usar arquivos de configuração ou variáveis de ambiente para armazenar credenciais.

3. Tratamento de Exceções
Erro:
catch (Exception e) { }

Correção:
catch (Exception e) {
    e.printStackTrace();
}

Descrição:
As exceções estão sendo capturadas, mas não tratadas nem registradas. Adicionar logging para capturar as exceções facilita a identificação de erros.

4. Recurso Não Fechado
Erro:
A conexão ao banco de dados (conn) e o Statement não são fechados após o uso.

Correção:
finally {
    try {
        if (rs != null) rs.close();
        if (st != null) st.close();
        if (conn != null) conn.close();
    } catch (Exception e) {
        e.printStackTrace();
    }
}

Descrição:
Não fechar recursos de banco de dados pode levar a vazamento de recursos e problemas de desempenho.

5. Concatenando Strings para SQL
Erro:
sql += "select nome from usuarios where login = '" + login + "' and senha = '" + senha + "';";

Correção:
String sql = "select nome from usuarios where login = ? and senha = ?";
PreparedStatement pstmt = conn.prepareStatement(sql);
pstmt.setString(1, login);
pstmt.setString(2, senha);
ResultSet rs = pstmt.executeQuery();
Descrição:
Concatenar strings diretamente para criar consultas SQL pode levar a vulnerabilidades de injeção de SQL. Usar PreparedStatement para prevenir essas vulnerabilidades.