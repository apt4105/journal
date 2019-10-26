# journal
an online journal

# GET /asset/:user/:path

if `:path` points to a file, write the file as a response
if `:path` points to a directory, return a JSON array of strings


`:path` points to a directory iff it ends with a `/`

# PUT /asset/:user/:path

write the request's body to `:path` in the user's directory


