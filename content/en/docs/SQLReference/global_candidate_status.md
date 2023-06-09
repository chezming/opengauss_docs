# GLOBAL\_CANDIDATE\_STATUS<a name="EN-US_TOPIC_0000001150694716"></a>

**GLOBAL\_CANDIDATE\_STATUS**  displays the number of candidate buffers and buffer eviction information of all instances in the database.

**Table  1**  GLOBAL\_GET\_BGWRITER\_STATUS columns

<a name="table95071716277"></a>
<table><thead align="left"><tr id="row650117172719"><th class="cellrowborder" valign="top" width="22.55%" id="mcps1.2.4.1.1"><p id="p1505176271"><a name="p1505176271"></a><a name="p1505176271"></a>Name</p>
</th>
<th class="cellrowborder" valign="top" width="20.69%" id="mcps1.2.4.1.2"><p id="p350141722716"><a name="p350141722716"></a><a name="p350141722716"></a>Type</p>
</th>
<th class="cellrowborder" valign="top" width="56.76%" id="mcps1.2.4.1.3"><p id="p150141710279"><a name="p150141710279"></a><a name="p150141710279"></a>Description</p>
</th>
</tr>
</thead>
<tbody><tr id="row150181752713"><td class="cellrowborder" valign="top" width="22.55%" headers="mcps1.2.4.1.1 "><p id="p20501717152716"><a name="p20501717152716"></a><a name="p20501717152716"></a>node_name</p>
</td>
<td class="cellrowborder" valign="top" width="20.69%" headers="mcps1.2.4.1.2 "><p id="p165031792718"><a name="p165031792718"></a><a name="p165031792718"></a>text</p>
</td>
<td class="cellrowborder" valign="top" width="56.76%" headers="mcps1.2.4.1.3 "><p id="p145010176270"><a name="p145010176270"></a><a name="p145010176270"></a>Node name</p>
</td>
</tr>
<tr id="row1850161732714"><td class="cellrowborder" valign="top" width="22.55%" headers="mcps1.2.4.1.1 "><p id="p450817152719"><a name="p450817152719"></a><a name="p450817152719"></a>candidate_slots</p>
</td>
<td class="cellrowborder" valign="top" width="20.69%" headers="mcps1.2.4.1.2 "><p id="p077918823010"><a name="p077918823010"></a><a name="p077918823010"></a>integer</p>
</td>
<td class="cellrowborder" valign="top" width="56.76%" headers="mcps1.2.4.1.3 "><p id="p145071752718"><a name="p145071752718"></a><a name="p145071752718"></a>Number of pages in the candidate buffer chain of the current normal buffer pool</p>
</td>
</tr>
<tr id="row13501017192710"><td class="cellrowborder" valign="top" width="22.55%" headers="mcps1.2.4.1.1 "><p id="p950141762710"><a name="p950141762710"></a><a name="p950141762710"></a>get_buf_from_list</p>
</td>
<td class="cellrowborder" valign="top" width="20.69%" headers="mcps1.2.4.1.2 "><p id="p135012174277"><a name="p135012174277"></a><a name="p135012174277"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.76%" headers="mcps1.2.4.1.3 "><p id="p550317192715"><a name="p550317192715"></a><a name="p550317192715"></a>Number of times that pages are obtained from the candidate buffer chain during buffer eviction in the current normal buffer pool</p>
</td>
</tr>
<tr id="row1750141772714"><td class="cellrowborder" valign="top" width="22.55%" headers="mcps1.2.4.1.1 "><p id="p16501517112711"><a name="p16501517112711"></a><a name="p16501517112711"></a>get_buf_clock_sweep</p>
</td>
<td class="cellrowborder" valign="top" width="20.69%" headers="mcps1.2.4.1.2 "><p id="p175041712716"><a name="p175041712716"></a><a name="p175041712716"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.76%" headers="mcps1.2.4.1.3 "><p id="p050617162714"><a name="p050617162714"></a><a name="p050617162714"></a>Number of times that pages are obtained from the original eviction solution during buffer eviction in the current normal buffer pool</p>
</td>
</tr>
<tr id="row19501317112710"><td class="cellrowborder" valign="top" width="22.55%" headers="mcps1.2.4.1.1 "><p id="p14501017202719"><a name="p14501017202719"></a><a name="p14501017202719"></a>seg_candidate_slots</p>
</td>
<td class="cellrowborder" valign="top" width="20.69%" headers="mcps1.2.4.1.2 "><p id="p16208824303"><a name="p16208824303"></a><a name="p16208824303"></a>integer</p>
</td>
<td class="cellrowborder" valign="top" width="56.76%" headers="mcps1.2.4.1.3 "><p id="p250121742718"><a name="p250121742718"></a><a name="p250121742718"></a>Number of pages in the candidate buffer chain of the current segment buffer pool</p>
</td>
</tr>
<tr id="row105041714277"><td class="cellrowborder" valign="top" width="22.55%" headers="mcps1.2.4.1.1 "><p id="p250717112710"><a name="p250717112710"></a><a name="p250717112710"></a>seg_get_buf_from_list</p>
</td>
<td class="cellrowborder" valign="top" width="20.69%" headers="mcps1.2.4.1.2 "><p id="p95117173277"><a name="p95117173277"></a><a name="p95117173277"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.76%" headers="mcps1.2.4.1.3 "><p id="p551101742718"><a name="p551101742718"></a><a name="p551101742718"></a>Number of times that pages are obtained from the candidate buffer chain during buffer eviction in the current segment buffer pool</p>
</td>
</tr>
<tr id="row12335949202917"><td class="cellrowborder" valign="top" width="22.55%" headers="mcps1.2.4.1.1 "><p id="p13352049102912"><a name="p13352049102912"></a><a name="p13352049102912"></a>seg_get_buf_clock_sweep</p>
</td>
<td class="cellrowborder" valign="top" width="20.69%" headers="mcps1.2.4.1.2 "><p id="p118599567297"><a name="p118599567297"></a><a name="p118599567297"></a>bigint</p>
</td>
<td class="cellrowborder" valign="top" width="56.76%" headers="mcps1.2.4.1.3 "><p id="p3336649132918"><a name="p3336649132918"></a><a name="p3336649132918"></a>Number of times that pages are obtained from the original eviction solution during buffer eviction in the current segment buffer pool</p>
</td>
</tr>
</tbody>
</table>

