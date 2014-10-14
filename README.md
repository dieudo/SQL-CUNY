607Project3
===========

#Dieudonne Ouedraogo
#I created this database on my computer
- Database: "607week7"

-- DROP DATABASE "607week7";

CREATE DATABASE "607week7"
  WITH OWNER = postgres
       ENCODING = 'UTF8'
       TABLESPACE = pg_default
       LC_COLLATE = 'English_United States.1252'
       LC_CTYPE = 'English_United States.1252'
       CONNECTION LIMIT = -1;
       
       
       #I created this table
       
       -- Table: wikidata2

-- DROP TABLE wikidata2;

CREATE TABLE wikidata2
(
  language text,
  "pageName" character varying,
  "pageView" integer,
  "sizeOfPage" numeric
)
WITH (
  OIDS=FALSE
);
ALTER TABLE wikidata2
  OWNER TO postgres;
  
  
  -- Column: language

-- ALTER TABLE wikidata2 DROP COLUMN language;

ALTER TABLE wikidata2 ADD COLUMN language text;
 Column: "pageName"

-- ALTER TABLE wikidata2 DROP COLUMN "pageName";

ALTER TABLE wikidata2 ADD COLUMN "pageName" character varying;

-- Column: "pageView"

-- ALTER TABLE wikidata2 DROP COLUMN "pageView";

ALTER TABLE wikidata2 ADD COLUMN "pageView" integer;
-- Column: "sizeOfPage"

-- ALTER TABLE wikidata2 DROP COLUMN "sizeOfPage";

ALTER TABLE wikidata2 ADD COLUMN "sizeOfPage" numeric;



# I went to the icon wikidata2 on the GUI pgAdamin and rigth click ,went to import ,a window open ,I selected the file I copied on my computer(2014100114000.txt) ,and #put the delimiter empty space' ' on the column options,click done and the data was downloaded to my postgres environement,i found 592 ROWS
  
# with this code I can get the 5 most visited pages:
SELECT *
FROM wikidata2
ORDER by pageView DESC
TOP 5

# using the GUI by going the table icon and using View/filter icon and selecting the appropriate column(pageView),
#I was able to identify the following result with a view:
 language   pageName             pageView       sizeOfPage
1)en        Database             257            14268896
2)en        Data:image...        220            1729420
3)en        Data                 203            8573050
4)en        Data_mining          196            15613111
5)en        Data_Protection      174            3733159
  
  
  
  
