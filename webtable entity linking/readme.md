These data are used for evaluating Webtable entity linking in the following paper:

Zhang, Z. 2017. Effective and efficient semantic table interpretation using tableminer+. Semantic Web 8 (6), 921-957

All data are described in Section 10.1 of the paper, unless otherwise stated:

* imdb_*.zip: the IMDB dataset, with cell entity and column header annotated using Freebase topics
* Limaye200.tar.gz: the Limaye200 dataset, with cell entity, column header, and column relation annotated using Freebase topics
* Limaye_complete.tar.gz: the complete Limaye dataset with table cells annotated using Freebase topics
* musicbrainz.tar.gz: the music brainz dataset with cell entity, column header, and column relation annotated using Freebase topics
* LimayeAll-Original_100TableInspection.tar.gz: the 100 randomly selected tables for the analysis described in Appendix C.

**NOTE 1**: Since Freebase has been shut down after the publication of this work and data, it is not possible to use the annotation gold standard directly. However, it is still possible to fetch entries from Wikidata using Freebase ids. For example, see [this thread] for a discussion of work-around.

Each dataset contains raw table content (webpages for IMDB and MusicBrainz; XML for Limaye) usually located in a folder called 'raw', and annotations usually located in a folder called 'gs'.

The 'gs' folder can further contain annotations for table cells (entities), column headers (header, named entity + property), and column relations (relation). The annotation files for each raw table is named after the same table filename, followed by and extension that looks like 'cell.keys' for table cell annotations; 'header.keys' for table column annotations; and 'relation.keys' for column-column relation annotations. Below we explain the format within each annotation files.


**.cell.keys example**
Each line in such a file may look like: '0,4=/m/027lf1', where '0,4' is the table cell index (content cell at row 0, column 4); and '/m/027lf1' is the Freebase topic id


**.header.keys example**
Each line in such a file may look like:

4=/cvg/cvg_publisher=/games/game_publisher -TAB- /business/business_operation -TAB- ___NE

where '4' indicates the column index; '/cvg/cvg_publisher=/games/game_publisher' indicates that there are two 'best' annotations (using Freebase topic) for this header, as separated by '='; '/business/business_operation' after the first TAB character indicates 'ok' annotations; '___NE' after the second TAB character indicates that this table column contains named entities.


**.relation.keys**
Example one: 1,3;3,1=/cvg/computer_videogame/platforms

where '1,3;3,1' means two possible directional relations, either from column 1 to 3, or from 3 to 1.


Example two: -3,1;1,3=/cvg/cvg_platform/games_on_this_platform

'-3,1;1,3' tells that among the two possible relations '1,3' or '3,1', column '1' is the main subject column

Other than this, the relation annotation could be read in the same way as column label


**LimayeAll-Origina_100TabeInspection**
Example:

1,1= -TAB- xtm=/m/02k4l6|Defender -TAB- xlev=/m/02k4l6|Defender -TAB- nm=/m/02_j1w|Defender

where '1,1' is the cell index (content cell at row 1, column 1); 'x' in 'xtm' means the annotation is correct; 'tm' in 'xtm' indicates TableMiner+, while 'lev' and 'nm' are the other two baselines B_lev and B_nm (please see the paper for details). Then the string after '=' indicates the Freebase topic id, and its string label. 


[this thread]: <https://stackoverflow.com/questions/33636215/how-can-i-query-wikidata-with-a-freebase-id-from-a-youtube-video>
[Ziqi Zhang]: <mailto:ziqi.zhang@sheffield.ac.uk>
