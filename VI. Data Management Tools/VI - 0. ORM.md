### What is ORM?
- Stand for Object Relation Mapping, it's such as a bridge between an object-oriented programming language and a relation database.

**Without using ORM**
- Without ORM, developers have to write raw SQL with the databases. This requires a good understanding of SQL syntax and database-speecific nuances. 

Example: 
```
import pg from 'pg';
const pool = new pg.Pool({
  user: 'username',
  host: 'localhost',
  database: 'mydb',
  password: 'password',
  port: 5432,
});
async function getUser(id) {
  const query = 'SELECT * FROM users WHERE id = $1';
  const values = [id];
  try {
    const res = await pool.query(query, values);
    return res.rows[0];
  } catch (err) {
    console.error(err);
    return null;
  }
}
export default async function handler(req, res) {
  const user = await getUser(req.query.id);
  res.status(200).json(user);
}
```

**With using ORM**
- Using ORM such as [[VI - Prisma]], developers will work with high-level object & methods rather than direct SQL queries.
- Prisma also supports connections and other boilerplate operations.

Example: 
1. *Define the model in Prisma schema:*
```
model User {
  id    Int    @id @default(autoincrement())
  name  String
  email String @unique
}
```

2. *Use Prisma Client to fetch data:*
```
import { PrismaClient } from '@prisma/client';

const prisma = new PrismaClient();

export default async function handler(req, res) {
  const user = await prisma.user.findUnique({
    where: { id: parseInt(req.query.id) },
  });
  res.status(200).json(user);
}
```

**Key points**

| Aspect            | ORM                                                        | Direct SQL                                                      |
|--------------|---------------------------------------|--------------------------------------------------|
| Abstraction Level | Provides a higher level of abstraction, working with objects and methods. | Requires manual writing and execution of queries.               |
| Safety            | Automatically handles many security aspects like SQL injection prevention. | Requires meticulous attention to security, especially SQL injection. |
| Productivity      | Boosts productivity by reducing the amount of boilerplate code. | Offers more control and can be optimized for performance but increases complexity. |
| Learning Curve    | Requires learning specific APIs and behaviors of the ORM.   | Requires understanding of SQL syntax and database behaviors.    |
