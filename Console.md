
# Retrieve cluster status

GET _cluster/health

#Create an index to save documents

PUT favorite_team

# To create a document I shoud use a POST request and the index name following with "_doc" key

POST favorite_team/_doc
{
  "name": "Juventus F.C",
  "coach": "Massimiliano Allegri"
}

# To assign a fixed ID to our document we should use ID after _doc key

POST favorite_team/_doc/1
{
  "name": "Inter",
  "coach": "Simone Inzaghi"
}

# I can create another version of my document!

PUT favorite_team/_doc/1
{
  "name": "Inter",
  "coach": "Carlo Ancelotti"
}

#To retrieve my document, I should use GET method and ID

GET favorite_team/_doc/1

# I can se POST request to update a document using _update operation

POST favorite_team/_update/1
{ 
  "doc": { 
    "coach": "undefined" 
  } 
}

# Now it is cleaning time!

DELETE favorite_team/_doc/1
