
### SQL 명령어 분류

| 분류 | 설명 | 예시 |
| --- | --- | --- |
| DML (Data Manipulation Language) | 데이터베이스 내의 데이터를 조작하는 데 사용되는 명령어 | SELECT, INSERT, UPDATE, DELETE |
| DDL (Data Definition Language) | 데이터베이스 구조를 정의하거나 수정하는 데 사용되는 명령어 | CREATE, ALTER, DROP |
| DCL (Data Control Language) | 데이터베이스 사용자의 권한을 제어하는 명령어 | GRANT, REVOKE |

### DML 예시 (자바 코드)

DML 명령어를 사용하여 데이터를 조회, 삽입, 업데이트 및 삭제하는 자바 코드 예시입니다.

#### SELECT 예시

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;

public class DMLSelectExample {
    public static void main(String[] args) {
        String url = "jdbc:mariadb://localhost:3306/sample_java2";
        String user = "root";
        String password = "3033";

        try (Connection connection = DriverManager.getConnection(url, user, password)) {
            String sql = "SELECT * FROM employees";
            try (PreparedStatement preparedStatement = connection.prepareStatement(sql)) {
                ResultSet resultSet = preparedStatement.executeQuery();
                while (resultSet.next()) {
                    int id = resultSet.getInt("id");
                    String name = resultSet.getString("name");
                    String position = resultSet.getString("position");
                    System.out.println("ID: " + id + ", Name: " + name + ", Position: " + position);
                }
            }
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
```

#### INSERT 예시

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;

public class DMLInsertExample {
    public static void main(String[] args) {
        String url = "jdbc:mariadb://localhost:3306/sample_java2";
        String user = "root";
        String password = "3033";

        try (Connection connection = DriverManager.getConnection(url, user, password)) {
            String sql = "INSERT INTO employees (id, name, position) VALUES (?, ?, ?)";
            try (PreparedStatement preparedStatement = connection.prepareStatement(sql)) {
                preparedStatement.setInt(1, 2);
                preparedStatement.setString(2, "Alice");
                preparedStatement.setString(3, "Engineer");
                preparedStatement.executeUpdate();
            }
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
```

#### UPDATE 예시

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;

public class DMLUpdateExample {
    public static void main(String[] args) {
        String url = "jdbc:mariadb://localhost:3306/sample_java2";
        String user = "root";
        String password = "3033";

        try (Connection connection = DriverManager.getConnection(url, user, password)) {
            String sql = "UPDATE employees SET position = ? WHERE id = ?";
            try (PreparedStatement preparedStatement = connection.prepareStatement(sql)) {
                preparedStatement.setString(1, "Senior Engineer");
                preparedStatement.setInt(2, 2);
                preparedStatement.executeUpdate();
            }
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
```

#### DELETE 예시

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;

public class DMLDeleteExample {
    public static void main(String[] args) {
        String url = "jdbc:mariadb://localhost:3306/sample_java2";
        String user = "root";
        String password = "3033";

        try (Connection connection = DriverManager.getConnection(url, user, password)) {
            String sql = "DELETE FROM employees WHERE id = ?";
            try (PreparedStatement preparedStatement = connection.prepareStatement(sql)) {
                preparedStatement.setInt(1, 2);
                preparedStatement.executeUpdate();
            }
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
```

### DDL 예시 (자바 코드)

DDL 명령어를 사용하여 데이터베이스 구조를 정의하거나 수정하는 자바 코드 예시입니다.

#### CREATE 예시

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.Statement;
import java.sql.SQLException;

public class DDLCreateExample {
    public static void main(String[] args) {
        String url = "jdbc:mariadb://localhost:3306/sample_java2";
        String user = "root";
        String password = "3033";

        try (Connection connection = DriverManager.getConnection(url, user, password);
             Statement statement = connection.createStatement()) {

            String sql = "CREATE TABLE departments ("
                    + "id INT PRIMARY KEY AUTO_INCREMENT, "
                    + "name VARCHAR(50) NOT NULL)";
            statement.executeUpdate(sql);
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
```

#### ALTER 예시

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.Statement;
import java.sql.SQLException;

public class DDLAlterExample {
    public static void main(String[] args) {
        String url = "jdbc:mariadb://localhost:3306/sample_java2";
        String user = "root";
        String password = "3033";

        try (Connection connection = DriverManager.getConnection(url, user, password);
             Statement statement = connection.createStatement()) {

            String sql = "ALTER TABLE employees ADD COLUMN department_id INT";
            statement.executeUpdate(sql);
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
```

#### DROP 예시

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.Statement;
import java.sql.SQLException;

public class DDLDropExample {
    public static void main(String[] args) {
        String url = "jdbc:mariadb://localhost:3306/sample_java2";
        String user = "root";
        String password = "3033";

        try (Connection connection = DriverManager.getConnection(url, user, password);
             Statement statement = connection.createStatement()) {

            String sql = "DROP TABLE departments";
            statement.executeUpdate(sql);
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
```

### DCL 예시 (자바 코드)

DCL 명령어를 사용하여 데이터베이스 사용자의 권한을 제어하는 자바 코드 예시입니다.

#### GRANT 예시

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.Statement;
import java.sql.SQLException;

public class DCLGrantExample {
    public static void main(String[] args) {
        String url = "jdbc:mariadb://localhost:3306/sample_java2";
        String user = "root";
        String password = "3033";

        try (Connection connection = DriverManager.getConnection(url, user, password);
             Statement statement = connection.createStatement()) {

            String sql = "GRANT SELECT, INSERT ON sample_java2.employees TO 'user'@'localhost'";
            statement.executeUpdate(sql);
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
```

#### REVOKE 예시

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.Statement;
import java.sql.SQLException;

public class DCLRevokeExample {
    public static void main(String[] args) {
        String url = "jdbc:mariadb://localhost:3306/sample_java2";
        String user = "root";
        String password = "3033";

        try (Connection connection = DriverManager.getConnection(url, user, password);
             Statement statement = connection.createStatement()) {

            String sql = "REVOKE SELECT, INSERT ON sample_java2.employees FROM 'user'@'localhost'";
            statement.executeUpdate(sql);
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
```

### 요약

위의 예제들은 DML, DDL, DCL 명령어를 사용하여 데이터를 조작하고, 데이터베이스 구조를 정의하거나 수정하며, 데이터베이스 사용자의 권한을 제어하는 방법을 보여줍니다. 각각의 코드 예시는 자바를 사용하여 SQL 명령어를 실행하는 방법을 설명합니다.