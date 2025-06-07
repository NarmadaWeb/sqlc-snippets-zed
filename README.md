# Sqlc and Postgres Snippets for Zed IDE.

Boost your database development productivity with this comprehensive collection of 50+ powerful snippets for PostgreSQL and SQLC. Designed to reduce boilerplate, enforce best practices, and speed up your workflow when working with modern SQL databases and the SQLC code generator.

## Features

*   **Comprehensive SQLC Coverage**: Snippets for all core SQLC operations (`:one`, `:many`, `:exec`, `:batchexec`), including common patterns like returning inserted IDs, pagination, and batch inserts.
*   **Advanced SQLC Patterns**: Tackle complex scenarios with snippets for JOINs with aggregation, JSONB queries, array operations, full-text search, and transaction blocks.
*   **PostgreSQL DDL Mastery**: Quickly scaffold tables (with audit columns), indexes, enums, functions, and triggers (like auto-updating `updated_at`).
*   **Modern PostgreSQL Types**: Easy-to-use snippets for `UUID`, `JSONB` (with defaults), `TEXT[]` arrays, and full-text search setup (`TSVECTOR`).
*   **SQLC Configuration**: A ready-to-use `sqlc.yaml` template for both Go (pgx/v5) and Kotlin, including common type overrides.
*   **SQLC v2 Ready**: Includes snippets leveraging SQLC v2 features like named parameters (`@param`) and batch operations with returning values.
*   **Performance & Optimization**: Snippets for `EXPLAIN ANALYZE`, partial indexes, expression indexes, and Row Level Security (RLS) setup.
*   **Migration & Utility**: Helpers for creating extensions, adding/dropping columns, and common SQL expressions.
*   **Clear Descriptions**: Each snippet comes with a concise description of its purpose.
*   **Placeholder Guidance**: Smart placeholders (`${1:name}`, `${2|option1,option2|}`) guide you through snippet completion.

## Installation

1.  Open **Zed Editor**.
2.  Go to the **Extensions** view (Ctrl+Shift+X or Cmd+Shift+X).
3.  Search for `[Your Extension Name Here - e.g., Sqlc Snippets]`.
4.  Click **Install**.
5.  wait for minute.

## Usage

Simply start typing the snippet `prefix` in a `.sql` file (or any filetype you configure snippets for, like `.yaml`, `.query.sql`), and Zed Extensions will suggest the available snippets. Press `Tab` or `Enter` to insert the snippet. Use `Tab` to navigate through the placeholders.

**Example:**

1.  Type `sqlcone` in a `.sql` file.
2.  Press `Tab`.
3.  The following snippet will be inserted:
    ```sql
    -- name: GetUser :one
    SELECT * FROM users
    WHERE id = $1;
    ```
4.  `GetUser` will be selected. Type your desired query name, then press `Tab` to move to `users`, and so on.

## Available Snippets

Here's a categorized list of the main snippets included:

### SQLC Core Templates

| Prefix     | Description                       |
| :--------- | :-------------------------------- |
| `sqlcone`  | Get single row by ID              |
| `sqlcmany` | Get paginated results             |
| `sqlcinsert`| Insert with returning columns     |
| `sqlcupdate`| Update record                     |
| `sqlcdelete`| Delete record                     |
| `sqlcbatch`| Batch insert operation            |

### SQLC Advanced Patterns

| Prefix     | Description                       |
| :--------- | :-------------------------------- |
| `sqlcjoin` | Join with aggregation             |
| `sqlcjson` | Query JSONB field                 |
| `sqlcarray`| Query array column                |
| `sqlcfts`  | Full-text search query            |
| `sqlctx`   | Transaction block                 |

### SQLC v2 Features

| Prefix        | Description                        |
| :------------ | :--------------------------------- |
| `sqlcv2`      | sqlc v2 named parameters           |
| `sqlcv2batch` | sqlc v2 batch with returning       |
| `sqlcv2type`  | sqlc v2 with custom types          |

### PostgreSQL DDL (Data Definition Language)

| Prefix      | Description                       |
| :---------- | :-------------------------------- |
| `pgtbl`     | Create table with audit columns   |
| `pgidx`     | Create index                      |
| `pgenum`    | Create enum type                  |
| `pgfunc`    | Create PL/pgSQL function          |
| `pgtrigger` | Auto-update timestamp trigger     |

### PostgreSQL Advanced DML & Queries

| Prefix        | Description                       |
| :------------ | :-------------------------------- |
| `pgcte`       | Common Table Expression           |
| `pgjsonb`     | JSONB column with default         |
| `pgarray`     | Text array column                 |
| `pgfts`       | Full-text search setup            |
| `pguuid`      | Generate UUID v4 (`gen_random_uuid()`) |

### SQLC Configuration & Comments

| Prefix       | Description                       |
| :----------- | :-------------------------------- |
| `sqlcconfig` | sqlc configuration template (`sqlc.yaml`) |
| `sqlcmodel`  | Add comments for sqlc model       |

### Migration Utilities

| Prefix     | Description                       |
| :--------- | :-------------------------------- |
| `pgext`    | Create PostgreSQL extension       |
| `pgaddcol` | Add column to table               |
| `pgdropcol`| Drop column from table            |

### Security

| Prefix    | Description                       |
| :-------- | :-------------------------------- |
| `pgrls`   | Row Level Security policy         |
| `pggrant` | Grant table permissions           |

### Performance & Indexing

| Prefix         | Description                       |
| :------------- | :-------------------------------- |
| `pgexpridx`    | Create index on expression        |
| `pgpartialidx` | Create partial index              |

### Utility & Testing Snippets

| Prefix        | Description                       |
| :------------ | :-------------------------------- |
| `pgexplain`   | Detailed query analysis (`EXPLAIN ANALYZE BUFFERS VERBOSE`) |
| `pgnow`       | Current timestamp (`NOW()`)         |
| `pginterval`  | Time interval                     |
| `pgjsonbuild` | Build JSONB object                |
| `pgarrayagg`  | Aggregate to array                |
| `pgbegin`     | Test transaction block (BEGIN/ROLLBACK) |

*(Note: The `pgexplain` prefix from the `TESTING` section is listed above due to its comprehensiveness. The original JSON has two `pgexplain` entries; this one includes `VERBOSE`.)*


## Why These Snippets?

*   **Reduce Syntax Errors**: Pre-defined structures minimize typos and syntax mistakes.
*   **Enforce Best Practices**: Snippets incorporate common patterns like audit columns, proper indexing, and SQLC naming conventions.
*   **Accelerate Development**: Spend less time writing boilerplate and more time on business logic.
*   **Full SQLC Compatibility**: Designed to work seamlessly with SQLC's query parsing and code generation.


## Contributing

Contributions are welcome! If you have a snippet that you think would be a great addition, or if you have improvements for existing ones:

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/your-feature-name`).
3.  Add or modify snippets in the `snippets/yaml.json` or `snippets/sql.json`file (or wherever the source JSON is kept).
4.  Commit your changes (`git commit -am 'Add some feature'`).
5.  Push to the branch (`git push origin feature/your-feature-name`).
6.  Create a new Pull Request.

Please ensure your snippets are well-formatted, include a clear `prefix` and `description`, and use placeholders effectively.

## License

MIT License.