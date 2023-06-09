# STATEMENT\_HISTORY<a name="EN-US_TOPIC_0301807366"></a>

**STATEMENT\_HISTORY**  displays information about execution statements on the current node. To query a view, you must have the  **sysadmin **or  **monitor admin**  permission. The result can be queried only in the system database but cannot be queried in the user database.

**Table  1**  STATEMENT\_HISTORY columns

<a name="table949020817280"></a>
<table><thead align="left"><tr id="row44901885283"><th class="cellrowborder" valign="top" width="22.132213221322132%" id="mcps1.2.4.1.1"><p id="p204912089289"><a name="p204912089289"></a><a name="p204912089289"></a>Name</p>
</th>
<th class="cellrowborder" valign="top" width="21.602160216021602%" id="mcps1.2.4.1.2"><p id="p17491108122820"><a name="p17491108122820"></a><a name="p17491108122820"></a>Type</p>
</th>
<th class="cellrowborder" valign="top" width="56.265626562656266%" id="mcps1.2.4.1.3"><p id="p13491282281"><a name="p13491282281"></a><a name="p13491282281"></a>Description</p>
</th>
</tr>
</thead>
<tbody><tr id="row16491158192819"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p1149178122814"><a name="p1149178122814"></a><a name="p1149178122814"></a>dbname</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p124911782289"><a name="p124911782289"></a><a name="p124911782289"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p1445326163513"><a name="p1445326163513"></a><a name="p1445326163513"></a>Database name.</p>
</td>
</tr>
<tr id="row14915892817"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p174910812286"><a name="p174910812286"></a><a name="p174910812286"></a>schemaname</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p1949128172817"><a name="p1949128172817"></a><a name="p1949128172817"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p164911589285"><a name="p164911589285"></a><a name="p164911589285"></a>Schema name.</p>
</td>
</tr>
<tr id="row749113817286"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p1749115882810"><a name="p1749115882810"></a><a name="p1749115882810"></a>origin_node</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p449148162820"><a name="p449148162820"></a><a name="p449148162820"></a>integer</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p16491108182819"><a name="p16491108182819"></a><a name="p16491108182819"></a>Node name.</p>
</td>
</tr>
<tr id="row649168132810"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p44917817289"><a name="p44917817289"></a><a name="p44917817289"></a>user_name</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p194912810285"><a name="p194912810285"></a><a name="p194912810285"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p134914811289"><a name="p134914811289"></a><a name="p134914811289"></a>Username.</p>
</td>
</tr>
<tr id="row249116815283"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p165338590242"><a name="p165338590242"></a><a name="p165338590242"></a>application_name</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p195321859102416"><a name="p195321859102416"></a><a name="p195321859102416"></a>text</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p105321759202415"><a name="p105321759202415"></a><a name="p105321759202415"></a>Name of the application that sends a request.</p>
</td>
</tr>
<tr id="row7491288288"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p1353125916241"><a name="p1353125916241"></a><a name="p1353125916241"></a>client_addr</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p14530125919243"><a name="p14530125919243"></a><a name="p14530125919243"></a>text</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p153025992418"><a name="p153025992418"></a><a name="p153025992418"></a>IP address of the client that sends a request.</p>
</td>
</tr>
<tr id="row1749158112812"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p1652975902410"><a name="p1652975902410"></a><a name="p1652975902410"></a>client_port</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p2529859102410"><a name="p2529859102410"></a><a name="p2529859102410"></a>integer</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p252865911245"><a name="p252865911245"></a><a name="p252865911245"></a>Port number of the client that sends a request.</p>
</td>
</tr>
<tr id="row148912328303"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p452716597243"><a name="p452716597243"></a><a name="p452716597243"></a>unique_query_id</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p115271059112417"><a name="p115271059112417"></a><a name="p115271059112417"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p1752618596243"><a name="p1752618596243"></a><a name="p1752618596243"></a>ID of the normalized SQL statement.</p>
</td>
</tr>
<tr id="row3770204193018"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p3525059192414"><a name="p3525059192414"></a><a name="p3525059192414"></a>debug_query_id</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p19525195982418"><a name="p19525195982418"></a><a name="p19525195982418"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p9524359162416"><a name="p9524359162416"></a><a name="p9524359162416"></a>ID of the unique SQL statement.</p>
</td>
</tr>
<tr id="row84341250185420"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p8434205005415"><a name="p8434205005415"></a><a name="p8434205005415"></a>query</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p3434155065416"><a name="p3434155065416"></a><a name="p3434155065416"></a>text</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p143412505544"><a name="p143412505544"></a><a name="p143412505544"></a>Normalized SQL statement.</p>
</td>
</tr>
<tr id="row3114174743016"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p10523459142411"><a name="p10523459142411"></a><a name="p10523459142411"></a>start_time</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p1752305914246"><a name="p1752305914246"></a><a name="p1752305914246"></a>timestamp with time zone</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p952265920244"><a name="p952265920244"></a><a name="p952265920244"></a>Time when a statement starts.</p>
</td>
</tr>
<tr id="row769485863017"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p155224594242"><a name="p155224594242"></a><a name="p155224594242"></a>finish_time</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p752117599242"><a name="p752117599242"></a><a name="p752117599242"></a>timestamp with time zone</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p1952065952411"><a name="p1952065952411"></a><a name="p1952065952411"></a>Time when a statement ends.</p>
</td>
</tr>
<tr id="row254515130314"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p1752095917241"><a name="p1752095917241"></a><a name="p1752095917241"></a>slow_sql_threshold</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p185191059122416"><a name="p185191059122416"></a><a name="p185191059122416"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p35181759122420"><a name="p35181759122420"></a><a name="p35181759122420"></a>Standard for slow SQL statement execution.</p>
</td>
</tr>
<tr id="row4589123123110"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p4518559182412"><a name="p4518559182412"></a><a name="p4518559182412"></a>transaction_id</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p5517185952411"><a name="p5517185952411"></a><a name="p5517185952411"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p2517125922414"><a name="p2517125922414"></a><a name="p2517125922414"></a>Transaction ID.</p>
</td>
</tr>
<tr id="row858902319313"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p15516145982414"><a name="p15516145982414"></a><a name="p15516145982414"></a>thread_id</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p20515659162415"><a name="p20515659162415"></a><a name="p20515659162415"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p55151659102410"><a name="p55151659102410"></a><a name="p55151659102410"></a>ID of an execution thread.</p>
</td>
</tr>
<tr id="row358810234313"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p1251416594243"><a name="p1251416594243"></a><a name="p1251416594243"></a>session_id</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p205131359172418"><a name="p205131359172418"></a><a name="p205131359172418"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p185131159202420"><a name="p185131159202420"></a><a name="p185131159202420"></a>Session ID of a user.</p>
</td>
</tr>
<tr id="row1858812314315"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p35121459142416"><a name="p35121459142416"></a><a name="p35121459142416"></a>n_soft_parse</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p105113599242"><a name="p105113599242"></a><a name="p105113599242"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p172795294391"><a name="p172795294391"></a><a name="p172795294391"></a>Number of soft parsing times. The value of <strong id="b207411632751"><a name="b207411632751"></a><a name="b207411632751"></a>n_soft_parse</strong> plus the value of <strong id="b17746732556"><a name="b17746732556"></a><a name="b17746732556"></a>n_hard_parse</strong> may be greater than the value of <strong id="b1574610321852"><a name="b1574610321852"></a><a name="b1574610321852"></a>n_calls</strong> because the number of subqueries is not counted in the value of <strong id="b15747113216516"><a name="b15747113216516"></a><a name="b15747113216516"></a>n_calls</strong>.</p>
</td>
</tr>
<tr id="row13775115215319"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p135106596249"><a name="p135106596249"></a><a name="p135106596249"></a>n_hard_parse</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p951015915249"><a name="p951015915249"></a><a name="p951015915249"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p18230133983919"><a name="p18230133983919"></a><a name="p18230133983919"></a>Number of hard parsing times. The value of <strong id="b1358717331256"><a name="b1358717331256"></a><a name="b1358717331256"></a>n_soft_parse</strong> plus the value of <strong id="b55881633952"><a name="b55881633952"></a><a name="b55881633952"></a>n_hard_parse</strong> may be greater than the value of <strong id="b18588103316510"><a name="b18588103316510"></a><a name="b18588103316510"></a>n_calls</strong> because the number of subqueries is not counted in the value of <strong id="b2058813331056"><a name="b2058813331056"></a><a name="b2058813331056"></a>n_calls</strong>.</p>
</td>
</tr>
<tr id="row877515216319"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p135081059162412"><a name="p135081059162412"></a><a name="p135081059162412"></a>query_plan</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p18508185911243"><a name="p18508185911243"></a><a name="p18508185911243"></a>text</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p150795912247"><a name="p150795912247"></a><a name="p150795912247"></a>Statement execution plan.</p>
</td>
</tr>
<tr id="row17775052123118"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p1250610593248"><a name="p1250610593248"></a><a name="p1250610593248"></a>n_returned_rows</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p1150610599240"><a name="p1150610599240"></a><a name="p1150610599240"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p19505155942415"><a name="p19505155942415"></a><a name="p19505155942415"></a>Number of rows in the result set returned by the <strong id="b1756133516518"><a name="b1756133516518"></a><a name="b1756133516518"></a>SELECT</strong> statement.</p>
</td>
</tr>
<tr id="row1977515273114"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p45042059132410"><a name="p45042059132410"></a><a name="p45042059132410"></a>n_tuples_fetched</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p1450495913244"><a name="p1450495913244"></a><a name="p1450495913244"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p19503195917240"><a name="p19503195917240"></a><a name="p19503195917240"></a>Number of rows randomly scanned.</p>
</td>
</tr>
<tr id="row1677535213111"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p250235912413"><a name="p250235912413"></a><a name="p250235912413"></a>n_tuples_returned</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p185021959192418"><a name="p185021959192418"></a><a name="p185021959192418"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p350120599248"><a name="p350120599248"></a><a name="p350120599248"></a>Number of rows sequentially scanned.</p>
</td>
</tr>
<tr id="row777417524311"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p16500195992414"><a name="p16500195992414"></a><a name="p16500195992414"></a>n_tuples_inserted</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p1150019594246"><a name="p1150019594246"></a><a name="p1150019594246"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p948105916244"><a name="p948105916244"></a><a name="p948105916244"></a>Number of rows inserted.</p>
</td>
</tr>
<tr id="row677415293112"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p2498222251"><a name="p2498222251"></a><a name="p2498222251"></a>n_tuples_updated</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p749722192515"><a name="p749722192515"></a><a name="p749722192515"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p549713212254"><a name="p549713212254"></a><a name="p549713212254"></a>Number of rows updated.</p>
</td>
</tr>
<tr id="row1774185218312"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p749611272519"><a name="p749611272519"></a><a name="p749611272519"></a>n_tuples_deleted</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p349513202519"><a name="p349513202519"></a><a name="p349513202519"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p17495923250"><a name="p17495923250"></a><a name="p17495923250"></a>Number of rows deleted.</p>
</td>
</tr>
<tr id="row277420523319"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p94943242512"><a name="p94943242512"></a><a name="p94943242512"></a>n_blocks_fetched</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p749317222510"><a name="p749317222510"></a><a name="p749317222510"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p449282182511"><a name="p449282182511"></a><a name="p449282182511"></a>Number of buffer block access times.</p>
</td>
</tr>
<tr id="row57742052153113"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p749211282517"><a name="p749211282517"></a><a name="p749211282517"></a>n_blocks_hit</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p849132102510"><a name="p849132102510"></a><a name="p849132102510"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p749012242515"><a name="p749012242515"></a><a name="p749012242515"></a>Number of buffer block hits.</p>
</td>
</tr>
<tr id="row777455214319"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p184893272519"><a name="p184893272519"></a><a name="p184893272519"></a>db_time</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p24891427257"><a name="p24891427257"></a><a name="p24891427257"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p1771542215411"><a name="p1771542215411"></a><a name="p1771542215411"></a>Valid DB time, which is accumulated if multiple threads are involved (unit: μs).</p>
</td>
</tr>
<tr id="row197745525319"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p1448713252518"><a name="p1448713252518"></a><a name="p1448713252518"></a>cpu_time</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p15486922257"><a name="p15486922257"></a><a name="p15486922257"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p948622132512"><a name="p948622132512"></a><a name="p948622132512"></a>CPU time (unit: μs).</p>
</td>
</tr>
<tr id="row7761050202716"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p14761650132718"><a name="p14761650132718"></a><a name="p14761650132718"></a>execution_time</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p1276125014277"><a name="p1276125014277"></a><a name="p1276125014277"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p1976118507270"><a name="p1976118507270"></a><a name="p1976118507270"></a>Execution time in the executor (unit: μs).</p>
</td>
</tr>
<tr id="row96551157152710"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p765618575270"><a name="p765618575270"></a><a name="p765618575270"></a>parse_time</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p3656185752712"><a name="p3656185752712"></a><a name="p3656185752712"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p106561157142716"><a name="p106561157142716"></a><a name="p106561157142716"></a>SQL parsing time (unit: μs).</p>
</td>
</tr>
<tr id="row386316372814"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p98641331289"><a name="p98641331289"></a><a name="p98641331289"></a>plan_time</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p1686416312283"><a name="p1686416312283"></a><a name="p1686416312283"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p198640320288"><a name="p198640320288"></a><a name="p198640320288"></a>SQL plan generation time (unit: μs).</p>
</td>
</tr>
<tr id="row1236810134287"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p12368141313288"><a name="p12368141313288"></a><a name="p12368141313288"></a>rewrite_time</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p143681413202810"><a name="p143681413202810"></a><a name="p143681413202810"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p936861372810"><a name="p936861372810"></a><a name="p936861372810"></a>SQL rewriting time (unit: μs).</p>
</td>
</tr>
<tr id="row1831252022816"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p14312102010285"><a name="p14312102010285"></a><a name="p14312102010285"></a>pl_execution_time</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p63121020102811"><a name="p63121020102811"></a><a name="p63121020102811"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p33121020172816"><a name="p33121020172816"></a><a name="p33121020172816"></a>Execution time of PL/pgSQL (unit: μs).</p>
</td>
</tr>
<tr id="row12287162622811"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p18287182642811"><a name="p18287182642811"></a><a name="p18287182642811"></a>pl_compilation_time</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p1428782692815"><a name="p1428782692815"></a><a name="p1428782692815"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p628712617287"><a name="p628712617287"></a><a name="p628712617287"></a>Compilation time of PL/pgSQL (unit: μs).</p>
</td>
</tr>
<tr id="row9895133272810"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p12895193212813"><a name="p12895193212813"></a><a name="p12895193212813"></a>data_io_time</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p6895103242810"><a name="p6895103242810"></a><a name="p6895103242810"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p10895203212289"><a name="p10895203212289"></a><a name="p10895203212289"></a>I/O time (unit: μs).</p>
</td>
</tr>
<tr id="row19021825295"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p790215242915"><a name="p790215242915"></a><a name="p790215242915"></a>net_send_info</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p19022242917"><a name="p19022242917"></a><a name="p19022242917"></a>text</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p166675265421"><a name="p166675265421"></a><a name="p166675265421"></a>Network status of messages sent through a physical connection, including the time (unit: μs), number of calls, and throughput (unit: byte). This field can be used to analyze the network overhead of SQL in a distributed system. This field is not supported in a standalone mode. Example: {"time":xxx, "n_calls":xxx, "size":xxx}.</p>
</td>
</tr>
<tr id="row1597621252919"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p129761512172910"><a name="p129761512172910"></a><a name="p129761512172910"></a>net_recv_info</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p19976131232915"><a name="p19976131232915"></a><a name="p19976131232915"></a>text</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p16967114513427"><a name="p16967114513427"></a><a name="p16967114513427"></a>Network status of messages received through a physical connection, including the time (unit: μs), number of calls, and throughput (unit: byte). This field can be used to analyze the network overhead of SQL in a distributed system. This field is not supported in a standalone mode. Example: {"time":xxx, "n_calls":xxx, "size":xxx}.</p>
</td>
</tr>
<tr id="row2051215917299"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p2051269132917"><a name="p2051269132917"></a><a name="p2051269132917"></a>net_stream_send_info</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p1451215911291"><a name="p1451215911291"></a><a name="p1451215911291"></a>text</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p695315818427"><a name="p695315818427"></a><a name="p695315818427"></a>Network status of messages sent through a logical connection, including the time (unit: μs), number of calls, and throughput (unit: byte). This field can be used to analyze the network overhead of SQL in a distributed system. This field is not supported in a standalone mode. Example: {"time":xxx, "n_calls":xxx, "size":xxx}.</p>
</td>
</tr>
<tr id="row1978203162913"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p167818317296"><a name="p167818317296"></a><a name="p167818317296"></a>net_stream_recv_info</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p1578173110298"><a name="p1578173110298"></a><a name="p1578173110298"></a>text</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p292014112436"><a name="p292014112436"></a><a name="p292014112436"></a>Network status of messages received through a logical connection, including the time (unit: μs), number of calls, and throughput (unit: byte). This field can be used to analyze the network overhead of SQL in a distributed system. This field is not supported in a standalone mode. Example: {"time":xxx, "n_calls":xxx, "size":xxx}.</p>
</td>
</tr>
<tr id="row15401123892910"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p154011138192918"><a name="p154011138192918"></a><a name="p154011138192918"></a>lock_count</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p1440123818299"><a name="p1440123818299"></a><a name="p1440123818299"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p840113386291"><a name="p840113386291"></a><a name="p840113386291"></a>Number of locks.</p>
</td>
</tr>
<tr id="row17958944152917"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p19958204410298"><a name="p19958204410298"></a><a name="p19958204410298"></a>lock_time</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p69582044122918"><a name="p69582044122918"></a><a name="p69582044122918"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p12958344142919"><a name="p12958344142919"></a><a name="p12958344142919"></a>Time required for locking.</p>
</td>
</tr>
<tr id="row4438148112918"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p1043884818295"><a name="p1043884818295"></a><a name="p1043884818295"></a>lock_wait_count</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p1743816482294"><a name="p1743816482294"></a><a name="p1743816482294"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p11438144832911"><a name="p11438144832911"></a><a name="p11438144832911"></a>Number of lock waits.</p>
</td>
</tr>
<tr id="row12165137203010"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p01662710309"><a name="p01662710309"></a><a name="p01662710309"></a>lock_wait_time</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p11166379302"><a name="p11166379302"></a><a name="p11166379302"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p2016677173010"><a name="p2016677173010"></a><a name="p2016677173010"></a>Time required for lock waiting.</p>
</td>
</tr>
<tr id="row1594391063014"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p139437103309"><a name="p139437103309"></a><a name="p139437103309"></a>lock_max_count</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p3943910163018"><a name="p3943910163018"></a><a name="p3943910163018"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p394311015303"><a name="p394311015303"></a><a name="p394311015303"></a>Maximum number of locks.</p>
</td>
</tr>
<tr id="row15933436143016"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p199331936153019"><a name="p199331936153019"></a><a name="p199331936153019"></a>lwlock_count</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p5933183683016"><a name="p5933183683016"></a><a name="p5933183683016"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p893393612304"><a name="p893393612304"></a><a name="p893393612304"></a>Number of lightweight locks (reserved).</p>
</td>
</tr>
<tr id="row92451440133019"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p624512407308"><a name="p624512407308"></a><a name="p624512407308"></a>lwlock_wait_count</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p1024613403300"><a name="p1024613403300"></a><a name="p1024613403300"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p162462407306"><a name="p162462407306"></a><a name="p162462407306"></a>Number of lightweight lock waits.</p>
</td>
</tr>
<tr id="row10701104318302"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p1470184333016"><a name="p1470184333016"></a><a name="p1470184333016"></a>lwlock_time</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p870104318305"><a name="p870104318305"></a><a name="p870104318305"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p17701543103012"><a name="p17701543103012"></a><a name="p17701543103012"></a>Time required for lightweight locking (reserved).</p>
</td>
</tr>
<tr id="row551915663018"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p25199565301"><a name="p25199565301"></a><a name="p25199565301"></a>lwlock_wait_time</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p8519145615307"><a name="p8519145615307"></a><a name="p8519145615307"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p195190563305"><a name="p195190563305"></a><a name="p195190563305"></a>Time required for lightweight locking.</p>
</td>
</tr>
<tr id="row1139711323112"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p73972034315"><a name="p73972034315"></a><a name="p73972034315"></a>details</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p339717319319"><a name="p339717319319"></a><a name="p339717319319"></a>bytea</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p43971231315"><a name="p43971231315"></a><a name="p43971231315"></a>List of statement lock events, which are recorded in time sequence. The number of records is affected by the <strong id="b914110141568"><a name="b914110141568"></a><a name="b914110141568"></a>track_stmt_details_size </strong>parameter.</p>
<p id="p206443813496"><a name="p206443813496"></a><a name="p206443813496"></a>Events include:</p>
<a name="ul452445214189"></a><a name="ul452445214189"></a><ul id="ul452445214189"><li>Start locking.</li><li>Complete locking.</li><li>Start lock waiting.</li><li>Complete lock waiting.</li><li>Start unlocking.</li><li>Complete unlocking.</li><li>Start lightweight lock waiting.</li><li>Complete lightweight lock waiting.</li></ul>
</td>
</tr>
<tr id="row19936171305317"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p14936191313534"><a name="p14936191313534"></a><a name="p14936191313534"></a>is_slow_sql</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p179367131531"><a name="p179367131531"></a><a name="p179367131531"></a>boolean</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p159361013155319"><a name="p159361013155319"></a><a name="p159361013155319"></a>Whether the SQL statement is a slow SQL statement.</p>
</td>
</tr>
<tr id="row13345818197"><td class="cellrowborder" valign="top" width="22.132213221322132%" headers="mcps1.2.4.1.1 "><p id="p43341816198"><a name="p43341816198"></a><a name="p43341816198"></a>trace_id</p>
</td>
<td class="cellrowborder" valign="top" width="21.602160216021602%" headers="mcps1.2.4.1.2 "><p id="p2033468171918"><a name="p2033468171918"></a><a name="p2033468171918"></a>text</p>
</td>
<td class="cellrowborder" valign="top" width="56.265626562656266%" headers="mcps1.2.4.1.3 "><p id="p1233419891920"><a name="p1233419891920"></a><a name="p1233419891920"></a>Driver-specific trace ID, which is associated with an application request.</p>
</td>
</tr>
</tbody>
</table>

