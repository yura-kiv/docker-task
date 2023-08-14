# This is a note list application API.
Two images are created using docker:
1) Server (Node.JS + TypeScript) on 8080 PORT
2) Database (<b>PostgreSQL</b> used docker image) on 5432 PORT

## All docker settings you can find at docker-compose file

Two containers are created that communicate with each other and can save, delete, edit records.

## Used technologies:
<ul>
  <li>Docker</li>
  <li>pg (PostgreSQL for Node.JS)</li>
  <li>Node.JS</li>
  <li>TypeScript</li>
  <li>Express.JS</li>
  <li>yup</li>
  <li>nodemon</li>  
</ul>

## To build images:
docker-compose build

## To run containers:
docker-compose up

## Example of SQL request:
<code>
export const getAllNotes = async (): Promise<Note[]> => {
  const query = `SELECT * FROM ${table}`;
  const result = await client.query(query);
  return result.rows;
};
</code>
<code>
export const getNoteById = async (id: string): Promise<Note | undefined> => {
  const query = `SELECT * FROM ${table} WHERE id = $1`;
  const result = await client.query(query, [id]);
  return result.rows[0];
};
</code>
