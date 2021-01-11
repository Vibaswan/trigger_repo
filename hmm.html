<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8"/>
    <title>Test Report</title>
    <style>body {
  font-family: Helvetica, Arial, sans-serif;
  font-size: 12px;
  /* do not increase min-width as some may use split screens */
  min-width: 800px;
  color: #999;
}

h1 {
  font-size: 24px;
  color: black;
}

h2 {
  font-size: 16px;
  color: black;
}

p {
  color: black;
}

a {
  color: #999;
}

table {
  border-collapse: collapse;
}

/******************************
 * SUMMARY INFORMATION
 ******************************/
#environment td {
  padding: 5px;
  border: 1px solid #E6E6E6;
}
#environment tr:nth-child(odd) {
  background-color: #f6f6f6;
}

/******************************
 * TEST RESULT COLORS
 ******************************/
span.passed,
.passed .col-result {
  color: green;
}

span.skipped,
span.xfailed,
span.rerun,
.skipped .col-result,
.xfailed .col-result,
.rerun .col-result {
  color: orange;
}

span.error,
span.failed,
span.xpassed,
.error .col-result,
.failed .col-result,
.xpassed .col-result {
  color: red;
}

/******************************
 * RESULTS TABLE
 *
 * 1. Table Layout
 * 2. Extra
 * 3. Sorting items
 *
 ******************************/
/*------------------
 * 1. Table Layout
 *------------------*/
#results-table {
  border: 1px solid #e6e6e6;
  color: #999;
  font-size: 12px;
  width: 100%;
}
#results-table th,
#results-table td {
  padding: 5px;
  border: 1px solid #E6E6E6;
  text-align: left;
}
#results-table th {
  font-weight: bold;
}

/*------------------
 * 2. Extra
 *------------------*/
.log {
  background-color: #e6e6e6;
  border: 1px solid #e6e6e6;
  color: black;
  display: block;
  font-family: "Courier New", Courier, monospace;
  height: 230px;
  overflow-y: scroll;
  padding: 5px;
  white-space: pre-wrap;
}
.log:only-child {
  height: inherit;
}

div.image {
  border: 1px solid #e6e6e6;
  float: right;
  height: 240px;
  margin-left: 5px;
  overflow: hidden;
  width: 320px;
}
div.image img {
  width: 320px;
}

div.video {
  border: 1px solid #e6e6e6;
  float: right;
  height: 240px;
  margin-left: 5px;
  overflow: hidden;
  width: 320px;
}
div.video video {
  overflow: hidden;
  width: 320px;
  height: 240px;
}

.collapsed {
  display: none;
}

.expander::after {
  content: " (show details)";
  color: #BBB;
  font-style: italic;
  cursor: pointer;
}

.collapser::after {
  content: " (hide details)";
  color: #BBB;
  font-style: italic;
  cursor: pointer;
}

/*------------------
 * 3. Sorting items
 *------------------*/
.sortable {
  cursor: pointer;
}

.sort-icon {
  font-size: 0px;
  float: left;
  margin-right: 5px;
  margin-top: 5px;
  /*triangle*/
  width: 0;
  height: 0;
  border-left: 8px solid transparent;
  border-right: 8px solid transparent;
}
.inactive .sort-icon {
  /*finish triangle*/
  border-top: 8px solid #E6E6E6;
}
.asc.active .sort-icon {
  /*finish triangle*/
  border-bottom: 8px solid #999;
}
.desc.active .sort-icon {
  /*finish triangle*/
  border-top: 8px solid #999;
}
</style></head>
  <body onLoad="init()">
    <script>/* This Source Code Form is subject to the terms of the Mozilla Public
 * License, v. 2.0. If a copy of the MPL was not distributed with this file,
 * You can obtain one at http://mozilla.org/MPL/2.0/. */


function toArray(iter) {
    if (iter === null) {
        return null;
    }
    return Array.prototype.slice.call(iter);
}

function find(selector, elem) { // eslint-disable-line no-redeclare
    if (!elem) {
        elem = document;
    }
    return elem.querySelector(selector);
}

function findAll(selector, elem) {
    if (!elem) {
        elem = document;
    }
    return toArray(elem.querySelectorAll(selector));
}

function sortColumn(elem) {
    toggleSortStates(elem);
    const colIndex = toArray(elem.parentNode.childNodes).indexOf(elem);
    let key;
    if (elem.classList.contains('result')) {
        key = keyResult;
    } else if (elem.classList.contains('links')) {
        key = keyLink;
    } else {
        key = keyAlpha;
    }
    sortTable(elem, key(colIndex));
}

function showAllExtras() { // eslint-disable-line no-unused-vars
    findAll('.col-result').forEach(showExtras);
}

function hideAllExtras() { // eslint-disable-line no-unused-vars
    findAll('.col-result').forEach(hideExtras);
}

function showExtras(colresultElem) {
    const extras = colresultElem.parentNode.nextElementSibling;
    const expandcollapse = colresultElem.firstElementChild;
    extras.classList.remove('collapsed');
    expandcollapse.classList.remove('expander');
    expandcollapse.classList.add('collapser');
}

function hideExtras(colresultElem) {
    const extras = colresultElem.parentNode.nextElementSibling;
    const expandcollapse = colresultElem.firstElementChild;
    extras.classList.add('collapsed');
    expandcollapse.classList.remove('collapser');
    expandcollapse.classList.add('expander');
}

function showFilters() {
    const filterItems = document.getElementsByClassName('filter');
    for (let i = 0; i < filterItems.length; i++)
        filterItems[i].hidden = false;
}

function addCollapse() {
    // Add links for show/hide all
    const resulttable = find('table#results-table');
    const showhideall = document.createElement('p');
    showhideall.innerHTML = '<a href="javascript:showAllExtras()">Show all details</a> / ' +
                            '<a href="javascript:hideAllExtras()">Hide all details</a>';
    resulttable.parentElement.insertBefore(showhideall, resulttable);

    // Add show/hide link to each result
    findAll('.col-result').forEach(function(elem) {
        const collapsed = getQueryParameter('collapsed') || 'Passed';
        const extras = elem.parentNode.nextElementSibling;
        const expandcollapse = document.createElement('span');
        if (extras.classList.contains('collapsed')) {
            expandcollapse.classList.add('expander');
        } else if (collapsed.includes(elem.innerHTML)) {
            extras.classList.add('collapsed');
            expandcollapse.classList.add('expander');
        } else {
            expandcollapse.classList.add('collapser');
        }
        elem.appendChild(expandcollapse);

        elem.addEventListener('click', function(event) {
            if (event.currentTarget.parentNode.nextElementSibling.classList.contains('collapsed')) {
                showExtras(event.currentTarget);
            } else {
                hideExtras(event.currentTarget);
            }
        });
    });
}

function getQueryParameter(name) {
    const match = RegExp('[?&]' + name + '=([^&]*)').exec(window.location.search);
    return match && decodeURIComponent(match[1].replace(/\+/g, ' '));
}

function init () { // eslint-disable-line no-unused-vars
    resetSortHeaders();

    addCollapse();

    showFilters();

    sortColumn(find('.initial-sort'));

    findAll('.sortable').forEach(function(elem) {
        elem.addEventListener('click',
            function() {
                sortColumn(elem);
            }, false);
    });
}

function sortTable(clicked, keyFunc) {
    const rows = findAll('.results-table-row');
    const reversed = !clicked.classList.contains('asc');
    const sortedRows = sort(rows, keyFunc, reversed);
    /* Whole table is removed here because browsers acts much slower
     * when appending existing elements.
     */
    const thead = document.getElementById('results-table-head');
    document.getElementById('results-table').remove();
    const parent = document.createElement('table');
    parent.id = 'results-table';
    parent.appendChild(thead);
    sortedRows.forEach(function(elem) {
        parent.appendChild(elem);
    });
    document.getElementsByTagName('BODY')[0].appendChild(parent);
}

function sort(items, keyFunc, reversed) {
    const sortArray = items.map(function(item, i) {
        return [keyFunc(item), i];
    });

    sortArray.sort(function(a, b) {
        const keyA = a[0];
        const keyB = b[0];

        if (keyA == keyB) return 0;

        if (reversed) {
            return keyA < keyB ? 1 : -1;
        } else {
            return keyA > keyB ? 1 : -1;
        }
    });

    return sortArray.map(function(item) {
        const index = item[1];
        return items[index];
    });
}

function keyAlpha(colIndex) {
    return function(elem) {
        return elem.childNodes[1].childNodes[colIndex].firstChild.data.toLowerCase();
    };
}

function keyLink(colIndex) {
    return function(elem) {
        const dataCell = elem.childNodes[1].childNodes[colIndex].firstChild;
        return dataCell == null ? '' : dataCell.innerText.toLowerCase();
    };
}

function keyResult(colIndex) {
    return function(elem) {
        const strings = ['Error', 'Failed', 'Rerun', 'XFailed', 'XPassed',
            'Skipped', 'Passed'];
        return strings.indexOf(elem.childNodes[1].childNodes[colIndex].firstChild.data);
    };
}

function resetSortHeaders() {
    findAll('.sort-icon').forEach(function(elem) {
        elem.parentNode.removeChild(elem);
    });
    findAll('.sortable').forEach(function(elem) {
        const icon = document.createElement('div');
        icon.className = 'sort-icon';
        icon.textContent = 'vvv';
        elem.insertBefore(icon, elem.firstChild);
        elem.classList.remove('desc', 'active');
        elem.classList.add('asc', 'inactive');
    });
}

function toggleSortStates(elem) {
    //if active, toggle between asc and desc
    if (elem.classList.contains('active')) {
        elem.classList.toggle('asc');
        elem.classList.toggle('desc');
    }

    //if inactive, reset all other functions and add ascending active
    if (elem.classList.contains('inactive')) {
        resetSortHeaders();
        elem.classList.remove('inactive');
        elem.classList.add('active');
    }
}

function isAllRowsHidden(value) {
    return value.hidden == false;
}

function filterTable(elem) { // eslint-disable-line no-unused-vars
    const outcomeAtt = 'data-test-result';
    const outcome = elem.getAttribute(outcomeAtt);
    const classOutcome = outcome + ' results-table-row';
    const outcomeRows = document.getElementsByClassName(classOutcome);

    for(let i = 0; i < outcomeRows.length; i++){
        outcomeRows[i].hidden = !elem.checked;
    }

    const rows = findAll('.results-table-row').filter(isAllRowsHidden);
    const allRowsHidden = rows.length == 0 ? true : false;
    const notFoundMessage = document.getElementById('not-found-message');
    notFoundMessage.hidden = !allRowsHidden;
}
</script>
    <h1>Report.html</h1>
    <p>Report generated on 10-Jan-2021 at 23:12:56 by <a href="https://pypi.python.org/pypi/pytest-html">pytest-html</a> v3.1.1</p>
    <h2>Environment</h2>
    <table id="environment">
      <tr>
        <td>CI</td>
        <td>true</td></tr>
      <tr>
        <td>Packages</td>
        <td>{"pluggy": "0.13.1", "py": "1.10.0", "pytest": "6.1.2"}</td></tr>
      <tr>
        <td>Platform</td>
        <td>Windows-2012ServerR2-6.3.9600-SP0</td></tr>
      <tr>
        <td>Plugins</td>
        <td>{"html": "3.1.1", "metadata": "1.11.0"}</td></tr>
      <tr>
        <td>Python</td>
        <td>3.6.4</td></tr></table>
    <h2>Summary</h2>
    <p>11 tests ran in 851.13 seconds. </p>
    <p class="filter" hidden="true">(Un)check the boxes to filter the results.</p><input checked="true" class="filter" data-test-result="passed" hidden="true" name="filter_checkbox" onChange="filterTable(this)" type="checkbox"/><span class="passed">10 passed</span>, <input checked="true" class="filter" data-test-result="skipped" disabled="true" hidden="true" name="filter_checkbox" onChange="filterTable(this)" type="checkbox"/><span class="skipped">0 skipped</span>, <input checked="true" class="filter" data-test-result="failed" hidden="true" name="filter_checkbox" onChange="filterTable(this)" type="checkbox"/><span class="failed">1 failed</span>, <input checked="true" class="filter" data-test-result="error" disabled="true" hidden="true" name="filter_checkbox" onChange="filterTable(this)" type="checkbox"/><span class="error">0 errors</span>, <input checked="true" class="filter" data-test-result="xfailed" disabled="true" hidden="true" name="filter_checkbox" onChange="filterTable(this)" type="checkbox"/><span class="xfailed">0 expected failures</span>, <input checked="true" class="filter" data-test-result="xpassed" disabled="true" hidden="true" name="filter_checkbox" onChange="filterTable(this)" type="checkbox"/><span class="xpassed">0 unexpected passes</span>
    <h2>Results</h2>
    <table id="results-table">
      <thead id="results-table-head">
        <tr>
          <th class="sortable result initial-sort" col="result">Result</th>
          <th class="sortable" col="name">Test</th>
          <th class="sortable" col="duration">Duration</th>
          <th class="sortable links" col="links">Links</th></tr>
        <tr hidden="true" id="not-found-message">
          <th colspan="4">No results found. Try to check the filters</th></tr></thead>
      <tbody class="failed results-table-row">
        <tr>
          <td class="col-result">Failed</td>
          <td class="col-name">config_tests/test_config_lag.py::test_add_lag_ports</td>
          <td class="col-duration">48.31</td>
          <td class="col-links"></td></tr>
        <tr>
          <td class="extra" colspan="4">
            <div class="log">connect_to_ixn = {&#x27;connection&#x27;: {&#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {...}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X... {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;status&#x27;: &#x27;1&#x27;, ...}<br/>ixiangpf_api = &lt;ixiangpf.IxiaNgpf object at 0x021F00F0&gt;<br/>ixiatcl_api = &lt;ixiatcl.IxiaTcl object at 0x0498B510&gt;<br/>ixia_error = &lt;class &#x27;ixiaerror.IxiaError&#x27;&gt;<br/><br/>    def test_add_lag_ports(connect_to_ixn, ixiangpf_api, ixiatcl_api, ixia_error):<br/>        print(connect_to_ixn)<br/>        vport_list = connect_to_ixn[&#x27;vport_list&#x27;].split(&#x27; &#x27;)<br/>        print(vport_list)<br/>    <br/>        port_handle = vport_list<br/>    <br/>        vport_list = []<br/>    <br/>        for each_porthandle in port_handle:<br/>            vporthandle_status = ixiangpf_api.convert_porthandle_to_vport(port_handle=each_porthandle)<br/>            vport_handle = vporthandle_status[&#x27;handle&#x27;].split(&#x27;-&#x27;)[-1]<br/>            vport_list.append(vport_handle)<br/>    <br/>        print(&#x27;adding lag ports&#x27;)<br/>        lag_1 = ixiangpf_api.emulation_lag_config(<br/>            mode                                        = &quot;create&quot;,<br/>            port_handle                                 = [vport_list[0], vport_list[1]],<br/>            active                                      = &quot;1&quot;,<br/>            lag_name                                    = &quot;&quot;&quot;LAG 1&quot;&quot;&quot;,<br/>            protocol_type                               = &quot;lag_port_lacp&quot;,<br/>        )<br/>        util.check_and_print_result(ixiatcl_api, ixia_error, &#x27;Lag Config&#x27;, lag_1)<br/>    <br/>        lag_handle_1 = lag_1[&#x27;lag_handle&#x27;]<br/>    <br/>        lag_2 = ixiangpf_api.emulation_lag_config(<br/>            mode                                        = &quot;create&quot;,<br/>            port_handle                                 = [vport_list[2], vport_list[3]],<br/>            active                                      = &quot;1&quot;,<br/>            lag_name                                    = &quot;&quot;&quot;LAG 1&quot;&quot;&quot;,<br/>            protocol_type                               = &quot;lag_port_lacp&quot;,<br/>            lacp_actor_key                              = &quot;1&quot;,<br/>            lacp_actor_port_num                         = &quot;1&quot;,<br/>            lacp_actor_key_step                         = &quot;0&quot;,<br/>            lacp_actor_port_num_step                    = &quot;0&quot;,<br/>            lacp_actor_port_priority                    = &quot;1&quot;,<br/>            lacp_actor_system_id                        = &quot;00:00:00:00:00:02&quot;,<br/>            lacp_actor_system_id_step                   = &quot;00:00:00:00:00:00&quot;,<br/>            lacp_administrative_key                     = &quot;1&quot;,<br/>            lacp_collecting_flag                        = &quot;1&quot;,<br/>            lacp_distributing_flag                      = &quot;1&quot;,<br/>            lacp_collector_max_delay                    = &quot;0&quot;,<br/>            lacp_inter_marker_pdu_delay                 = &quot;6&quot;,<br/>            lacp_activity                               = &quot;active&quot;,<br/>            lacp_timeout                                = &quot;0&quot;,<br/>            lacp_du_periodic_time_interval              = &quot;0&quot;,<br/>            lacp_marker_req_mode                        = &quot;fixed&quot;,<br/>            lacp_marker_res_wait_time                   = &quot;5&quot;,<br/>            lacp_send_marker_req_on_lag_change          = &quot;1&quot;,<br/>            lacp_inter_marker_pdu_delay_random_min      = &quot;1&quot;,<br/>            lacp_inter_marker_pdu_delay_random_max      = &quot;6&quot;,<br/>            lacp_send_periodic_marker_req               = &quot;0&quot;,<br/>            lacp_support_responding_to_marker           = &quot;1&quot;,<br/>            lacp_sync_flag                              = &quot;1&quot;,<br/>            lacp_aggregation_flag                       = &quot;1&quot;,<br/>            lacp_actor_system_priority                  = &quot;1&quot;,<br/>            mtu                                         = &quot;1500&quot;,<br/>            src_mac_addr                                = &quot;00.12.01.00.00.01&quot;,<br/>            vlan                                        = &quot;0&quot;,<br/>            vlan_id_count                               = &#x27;%s&#x27; % (&quot;1&quot;),<br/>            notify_mac_move                             = &quot;0&quot;,<br/>        )<br/>    <br/>        lag_handle_2 = lag_2[&#x27;lag_handle&#x27;]<br/>    <br/>        util.check_and_print_result(ixiatcl_api, ixia_error, &#x27;Lag Config&#x27;, lag_2)<br/>    <br/>        topology_1 = ixiangpf_api.topology_config(<br/>            topology_name      = &quot;&quot;&quot;Topology 1&quot;&quot;&quot;,<br/>            lag_handle         = lag_handle_1,<br/>        )<br/>    <br/>        util.check_and_print_result(ixiatcl_api, ixia_error, &#x27;Topology Config over Lag&#x27;, topology_1)<br/>        topology_handle_1 = topology_1[&#x27;topology_handle&#x27;]<br/>    <br/>        topology_2 = ixiangpf_api.topology_config(<br/>            topology_name      = &quot;&quot;&quot;Topology 1&quot;&quot;&quot;,<br/>            lag_handle         = lag_handle_2,<br/>        )<br/>    <br/>        util.check_and_print_result(ixiatcl_api, ixia_error, &#x27;Topology Config over Lag&#x27;, topology_2)<br/>        topology_handle_2 = topology_2[&#x27;topology_handle&#x27;]<br/>    <br/>        result = ixiangpf_api.topology_config(<br/>            topology_handle              = topology_handle_1,<br/>            device_group_name            = &quot;&quot;&quot;Device Group 1&quot;&quot;&quot;,<br/>            device_group_multiplier      = &quot;10&quot;,<br/>            device_group_enabled         = &quot;1&quot;,<br/>        )<br/>    <br/>        util.check_and_print_result(ixiatcl_api, ixia_error, &#x27;DG Config over Lag&#x27;, result)<br/>        dg_handle_1 = result[&#x27;device_group_handle&#x27;]<br/>    <br/>        result = ixiangpf_api.topology_config(<br/>            topology_handle              = topology_handle_2,<br/>            device_group_name            = &quot;&quot;&quot;Device Group 2&quot;&quot;&quot;,<br/>            device_group_multiplier      = &quot;10&quot;,<br/>            device_group_enabled         = &quot;1&quot;,<br/>        )<br/>    <br/>        util.check_and_print_result(ixiatcl_api, ixia_error, &#x27;DG Config over Lag&#x27;, result)<br/>        dg_handle_2 = result[&#x27;device_group_handle&#x27;]<br/>    <br/>    <br/>    <br/>        print(&#x27;Adding OSPF over lag&#x27;)<br/>        ospf_1 = ixiangpf_api.emulation_ospf_config(mode = &quot;create&quot;, handle = dg_handle_1)<br/>        util.check_and_print_result(ixiatcl_api, ixia_error, &#x27;OSPF Config over LAG&#x27;, ospf_1)<br/>        ospf_handle_1  = ospf_1[&#x27;ospfv2_handle&#x27;]<br/>    <br/>        ospf_2 = ixiangpf_api.emulation_ospf_config(mode = &quot;create&quot;, handle = dg_handle_2)<br/>        util.check_and_print_result(ixiatcl_api, ixia_error, &#x27;OSPF Config over LAG&#x27;, ospf_2)<br/>        ospf_handle_2  = ospf_2[&#x27;ospfv2_handle&#x27;]<br/>    <br/>        print(&#x27;Starting OSPF over lag&#x27;)<br/>        result = ixiangpf_api.test_control(action = &quot;start_all_protocols&quot;)<br/>&gt;       util.check_and_print_result(ixiatcl_api, ixia_error,&#x27;Start All Protocols&#x27;, result)<br/><br/>tests\config_tests\test_config_lag.py:123: <br/>_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _<br/>tests\utils\common_utility.py:14: in check_and_print_result<br/>    error_handler(ixiatcl_api, ixia_error, api_name, result)<br/>_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _<br/><br/>ixiatcl_api = &lt;ixiatcl.IxiaTcl object at 0x0498B510&gt;<br/>ixia_error = &lt;class &#x27;ixiaerror.IxiaError&#x27;&gt;, api_name = &#x27;Start All Protocols&#x27;<br/>result = {&#x27;log&#x27;: &#x27;ERROR in ::ixia::test_control: Failed to start Protocols !!!&#x27;, &#x27;status&#x27;: &#x27;0&#x27;}<br/><br/>    def error_handler(ixiatcl_api, ixia_error, api_name, result):<br/>    <br/>        &quot;&quot;&quot;<br/>        As the name suggests thi helper function helps use to log the error in a proper format<br/>        :param ixiatcl_api: ixiatcl_api: ixiatcl object which is needed for operations<br/>        :param ixia_error: ixia_error: the ixia object use to handle ixia specific errors<br/>        :param api_name: api_name: name of the api to be checked and included in the log<br/>        :param result: result is the return value of the api after execution<br/>        &quot;&quot;&quot;<br/>    <br/>        err = ixiatcl_api.tcl_error_info()<br/>        log = result[&#x27;log&#x27;]<br/>        additional_info = &#x27;&gt; command: %s\n&gt; tcl errorInfo: %s\n&gt; log: %s&#x27; % (api_name, err, log)<br/>&gt;       raise ixia_error(ixia_error.COMMAND_FAIL, additional_info)<br/><span class="error">E       ixiaerror.IxiaError: HLTAPI command failed</span><br/><span class="error">E       Additional error info:</span><br/><span class="error">E       &gt; command: Start All Protocols</span><br/><span class="error">E       &gt; tcl errorInfo: </span><br/><span class="error">E       &gt; log: ERROR in ::ixia::test_control: Failed to start Protocols !!!</span><br/><br/>tests\utils\common_utility.py:32: IxiaError<br/> -----------------------------Captured stdout setup------------------------------ <br/>ixiatcl:info: Tcl version: 8.6.6
otg(username=None, password=None, api_server=&#x27;10.39.47.41:8888&#x27;, chassis=&#x27;10.39.35.12&#x27;, ports=[&#x27;2/13&#x27;, &#x27;2/14&#x27;, &#x27;2/15&#x27;, &#x27;2/16&#x27;])
{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
<br/> ------------------------------Captured stdout call------------------------------ <br/>{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
[&#x27;1/2/13&#x27;, &#x27;1/2/14&#x27;, &#x27;1/2/15&#x27;, &#x27;1/2/16&#x27;]
adding lag ports
ixiangpf:info: [01/10/2021 23:05:31    info] COMPLETED: emulation_lag_config           : PASS
Lag Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;lag_handle&#x27;: &#x27;/lag:5&#x27;, &#x27;protocol_stack_handle&#x27;: &#x27;/lag:5/protocolStack&#x27;, &#x27;ethernet_handle&#x27;: &#x27;/lag:5/protocolStack/ethernet:1&#x27;, &#x27;lag_port_lacp_handle&#x27;: &#x27;/lag:5/protocolStack/ethernet:1/lagportlacp:1&#x27;, &#x27;handle&#x27;: &#x27;/lag:5/protocolStack/ethernet:1/lagportlacp:1/item:1 /lag:5/protocolStack/ethernet:1/lagportlacp:1/item:2&#x27;}
ixiangpf:info: [01/10/2021 23:05:32    info] COMPLETED: emulation_lag_config           : PASS
Lag Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;lag_handle&#x27;: &#x27;/lag:6&#x27;, &#x27;protocol_stack_handle&#x27;: &#x27;/lag:6/protocolStack&#x27;, &#x27;ethernet_handle&#x27;: &#x27;/lag:6/protocolStack/ethernet:1&#x27;, &#x27;lag_port_lacp_handle&#x27;: &#x27;/lag:6/protocolStack/ethernet:1/lagportlacp:1&#x27;, &#x27;handle&#x27;: &#x27;/lag:6/protocolStack/ethernet:1/lagportlacp:1/item:1 /lag:6/protocolStack/ethernet:1/lagportlacp:1/item:2&#x27;}
ixiangpf:info: [01/10/2021 23:05:32    info] COMPLETED: topology_config                : PASS
Topology Config over Lag PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;topology_handle&#x27;: &#x27;/topology:1&#x27;}
ixiangpf:info: [01/10/2021 23:05:32    info] COMPLETED: topology_config                : PASS
Topology Config over Lag PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;topology_handle&#x27;: &#x27;/topology:2&#x27;}
ixiangpf:info: [01/10/2021 23:05:32    info] COMPLETED: topology_config                : PASS
DG Config over Lag PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;device_group_handle&#x27;: &#x27;/topology:1/deviceGroup:1&#x27;}
ixiangpf:info: [01/10/2021 23:05:32    info] COMPLETED: topology_config                : PASS
DG Config over Lag PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;device_group_handle&#x27;: &#x27;/topology:2/deviceGroup:1&#x27;}
Adding OSPF over lag
ixiangpf:info: [01/10/2021 23:05:32    info] COMPLETED: emulation_ospf_config          : PASS
OSPF Config over LAG PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;ethernet_handle&#x27;: &#x27;/topology:1/deviceGroup:1/ethernet:1&#x27;, &#x27;ipv4_handle&#x27;: &#x27;/topology:1/deviceGroup:1/ethernet:1/ipv4:1&#x27;, &#x27;ospfv2_handle&#x27;: &#x27;/topology:1/deviceGroup:1/ethernet:1/ipv4:1/ospfv2:1&#x27;}
ixiangpf:info: [01/10/2021 23:05:33    info] COMPLETED: emulation_ospf_config          : PASS
OSPF Config over LAG PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;ethernet_handle&#x27;: &#x27;/topology:2/deviceGroup:1/ethernet:1&#x27;, &#x27;ipv4_handle&#x27;: &#x27;/topology:2/deviceGroup:1/ethernet:1/ipv4:1&#x27;, &#x27;ospfv2_handle&#x27;: &#x27;/topology:2/deviceGroup:1/ethernet:1/ipv4:1/ospfv2:1&#x27;}
Starting OSPF over lag
ixiangpf:info: [01/10/2021 23:05:33    info] COMPLETED: test_control                   : PASS
<br/></div></td></tr></tbody>
      <tbody class="passed results-table-row">
        <tr>
          <td class="col-result">Passed</td>
          <td class="col-name">capture_tests/test_repetitive_capture.py::test_repetitive_captures</td>
          <td class="col-duration">108.03</td>
          <td class="col-links"></td></tr>
        <tr>
          <td class="extra" colspan="4">
            <div class="log"> -----------------------------Captured stdout setup------------------------------ <br/>ixiatcl:info: Tcl version: 8.6.6
otg(username=None, password=None, api_server=&#x27;10.39.47.41:8888&#x27;, chassis=&#x27;10.39.35.12&#x27;, ports=[&#x27;2/13&#x27;, &#x27;2/14&#x27;, &#x27;2/15&#x27;, &#x27;2/16&#x27;])
{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
<br/> ------------------------------Captured stdout call------------------------------ <br/>{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
[&#x27;1/2/13&#x27;, &#x27;1/2/14&#x27;, &#x27;1/2/15&#x27;, &#x27;1/2/16&#x27;]
creating traffic ......
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI0-HLTAPI_TRAFFICITEM_540&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
applying traffic first
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
configuring port for capture
Packet_Config_Buffers PASSED:: Log: {&#x27;port_handle&#x27;: &#x27;1/2/13&#x27;, &#x27;status&#x27;: &#x27;1&#x27;}
started iteration number ---------------------------------------------- 0
starting capture - 0
Packet_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;clicks&#x27;: &#x27;1932240828&#x27;, &#x27;seconds&#x27;: &#x27;1610348380&#x27;}
starting traffic - 0
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
waiting for some time - 0
stopping traffic - 0
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
stopping capture - 0
Packet_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;clicks&#x27;: &#x27;1941158333&#x27;, &#x27;seconds&#x27;: &#x27;1610348389&#x27;}
getting capture buffer state - 0
Packet_Control PASSED:: Log: {&#x27;capture_ready&#x27;: &#x27;1&#x27;, &#x27;status&#x27;: &#x27;1&#x27;, &#x27;clicks&#x27;: &#x27;1941171540&#x27;, &#x27;seconds&#x27;: &#x27;1610348389&#x27;}
Finished iteration number --------------------------------------------- 0
started iteration number ---------------------------------------------- 1
starting capture - 1
Packet_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;clicks&#x27;: &#x27;1942224458&#x27;, &#x27;seconds&#x27;: &#x27;1610348390&#x27;}
starting traffic - 1
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
waiting for some time - 1
stopping traffic - 1
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
stopping capture - 1
Packet_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;clicks&#x27;: &#x27;1952104129&#x27;, &#x27;seconds&#x27;: &#x27;1610348400&#x27;}
getting capture buffer state - 1
Packet_Control PASSED:: Log: {&#x27;capture_ready&#x27;: &#x27;1&#x27;, &#x27;status&#x27;: &#x27;1&#x27;, &#x27;clicks&#x27;: &#x27;1952115348&#x27;, &#x27;seconds&#x27;: &#x27;1610348400&#x27;}
Finished iteration number --------------------------------------------- 1
started iteration number ---------------------------------------------- 2
starting capture - 2
Packet_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;clicks&#x27;: &#x27;1952643048&#x27;, &#x27;seconds&#x27;: &#x27;1610348400&#x27;}
starting traffic - 2
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
waiting for some time - 2
stopping traffic - 2
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
stopping capture - 2
Packet_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;clicks&#x27;: &#x27;1963059110&#x27;, &#x27;seconds&#x27;: &#x27;1610348411&#x27;}
getting capture buffer state - 2
Packet_Control PASSED:: Log: {&#x27;capture_ready&#x27;: &#x27;1&#x27;, &#x27;status&#x27;: &#x27;1&#x27;, &#x27;clicks&#x27;: &#x27;1963069633&#x27;, &#x27;seconds&#x27;: &#x27;1610348411&#x27;}
Finished iteration number --------------------------------------------- 2
started iteration number ---------------------------------------------- 3
starting capture - 3
Packet_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;clicks&#x27;: &#x27;1963598122&#x27;, &#x27;seconds&#x27;: &#x27;1610348411&#x27;}
starting traffic - 3
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
waiting for some time - 3
stopping traffic - 3
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
stopping capture - 3
Packet_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;clicks&#x27;: &#x27;1974097021&#x27;, &#x27;seconds&#x27;: &#x27;1610348422&#x27;}
getting capture buffer state - 3
Packet_Control PASSED:: Log: {&#x27;capture_ready&#x27;: &#x27;1&#x27;, &#x27;status&#x27;: &#x27;1&#x27;, &#x27;clicks&#x27;: &#x27;1974107457&#x27;, &#x27;seconds&#x27;: &#x27;1610348422&#x27;}
Finished iteration number --------------------------------------------- 3
started iteration number ---------------------------------------------- 4
starting capture - 4
Packet_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;clicks&#x27;: &#x27;1974635042&#x27;, &#x27;seconds&#x27;: &#x27;1610348422&#x27;}
starting traffic - 4
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
waiting for some time - 4
stopping traffic - 4
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
stopping capture - 4
Packet_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;clicks&#x27;: &#x27;1985087070&#x27;, &#x27;seconds&#x27;: &#x27;1610348433&#x27;}
getting capture buffer state - 4
Packet_Control PASSED:: Log: {&#x27;capture_ready&#x27;: &#x27;1&#x27;, &#x27;status&#x27;: &#x27;1&#x27;, &#x27;clicks&#x27;: &#x27;1985097131&#x27;, &#x27;seconds&#x27;: &#x27;1610348433&#x27;}
Finished iteration number --------------------------------------------- 4
test complete!!!!
<br/></div></td></tr></tbody>
      <tbody class="passed results-table-row">
        <tr>
          <td class="col-result">Passed</td>
          <td class="col-name">config_tests/test_BUG1550565.py::test_topology_add_and_delete</td>
          <td class="col-duration">251.64</td>
          <td class="col-links"></td></tr>
        <tr>
          <td class="extra" colspan="4">
            <div class="log"> -----------------------------Captured stdout setup------------------------------ <br/>ixiatcl:info: Tcl version: 8.6.6
otg(username=None, password=None, api_server=&#x27;10.39.47.41:8888&#x27;, chassis=&#x27;10.39.35.12&#x27;, ports=[&#x27;2/13&#x27;, &#x27;2/14&#x27;, &#x27;2/15&#x27;, &#x27;2/16&#x27;])
{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
<br/> ------------------------------Captured stdout call------------------------------ <br/>{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
[&#x27;1/2/13&#x27;, &#x27;1/2/14&#x27;, &#x27;1/2/15&#x27;, &#x27;1/2/16&#x27;]
Resetting traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
clearing all stats
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Creating topology 1
ixiangpf:info: [01/10/2021 23:00:51    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;topology_handle&#x27;: &#x27;/topology:1&#x27;}
creating device group 1
ixiangpf:info: [01/10/2021 23:00:51    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;device_group_handle&#x27;: &#x27;/topology:1/deviceGroup:1&#x27;}
creating interface - eth and ip 1
ixiangpf:info: [01/10/2021 23:00:51    info] COMPLETED: interface_config               : PASS
Interface_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;ethernet_handle&#x27;: &#x27;/topology:1/deviceGroup:1/ethernet:1&#x27;, &#x27;ipv4_handle&#x27;: &#x27;/topology:1/deviceGroup:1/ethernet:1/ipv4:1&#x27;, &#x27;interface_handle&#x27;: &#x27;/topology:1/deviceGroup:1/ethernet:1/ipv4:1/item:1 /topology:1/deviceGroup:1/ethernet:1/item:1&#x27;}
starting device group 1
ixiangpf:info: [01/10/2021 23:00:51    info] COMPLETED: test_control                   : PASS
Test_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Creating topology 2
ixiangpf:info: [01/10/2021 23:00:51    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;topology_handle&#x27;: &#x27;/topology:2&#x27;}
creating device group 2
ixiangpf:info: [01/10/2021 23:00:51    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;device_group_handle&#x27;: &#x27;/topology:2/deviceGroup:1&#x27;}
creating interface - eth and ip 2
ixiangpf:info: [01/10/2021 23:00:51    info] COMPLETED: interface_config               : PASS
Interface_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;ethernet_handle&#x27;: &#x27;/topology:2/deviceGroup:1/ethernet:1&#x27;, &#x27;ipv4_handle&#x27;: &#x27;/topology:2/deviceGroup:1/ethernet:1/ipv4:1&#x27;, &#x27;interface_handle&#x27;: &#x27;/topology:2/deviceGroup:1/ethernet:1/ipv4:1/item:1 /topology:2/deviceGroup:1/ethernet:1/item:1&#x27;}
starting device group 2
ixiangpf:info: [01/10/2021 23:00:51    info] COMPLETED: test_control                   : PASS
Test_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Creating traffic 1
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI0-HLTAPI_TRAFFICITEM_540&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;udp-3&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;fcs-4&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;udp-3&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;fcs-4&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet.IPv4.UDP&#x27;}}
Creating traffic 2
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI1-HLTAPI_TRAFFICITEM_540&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:2/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:2/configElement:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:2/configElement:1/stack:&quot;udp-3&quot; ::ixNet::OBJ-/traffic/trafficItem:2/configElement:1/stack:&quot;fcs-4&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1/stack:&quot;udp-3&quot; ::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1/stack:&quot;fcs-4&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet.IPv4.UDP&#x27;}}
Creating traffic 3
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI2-HLTAPI_TRAFFICITEM_540&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:3/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:3/configElement:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:3/configElement:1/stack:&quot;udp-3&quot; ::ixNet::OBJ-/traffic/trafficItem:3/configElement:1/stack:&quot;fcs-4&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1/stack:&quot;udp-3&quot; ::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1/stack:&quot;fcs-4&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet.IPv4.UDP&#x27;}}
Creating traffic 4
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI3-HLTAPI_TRAFFICITEM_540&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:4/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:4/configElement:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:4/configElement:1/stack:&quot;udp-3&quot; ::ixNet::OBJ-/traffic/trafficItem:4/configElement:1/stack:&quot;fcs-4&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1/stack:&quot;udp-3&quot; ::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1/stack:&quot;fcs-4&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet.IPv4.UDP&#x27;}}
Applying traffic 1
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Running traffic 1
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Stopping traffic 1
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Applying traffic 2
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Running traffic 2
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Stopping traffic 2
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Applying traffic 3
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Running traffic 3
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Stopping traffic 3
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
setting send arp request to 1 for topology 1
ixiangpf:info: [01/10/2021 23:01:52    info] COMPLETED: interface_config               : PASS
Interface_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;/topology:1/deviceGroup:1/ethernet:1/ipv4:1/item:1&#x27;: {&#x27;arp_request_success&#x27;: &#x27;0&#x27;, &#x27;arp_failed_item_handles&#x27;: &#x27;{/topology:1/deviceGroup:1/ethernet:1/ipv4:1/item:1}&#x27;}}
setting send arp request to 1 for topology 2
ixiangpf:info: [01/10/2021 23:02:17    info] COMPLETED: interface_config               : PASS
Interface_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;/topology:2/deviceGroup:1/ethernet:1/ipv4:1/item:1&#x27;: {&#x27;arp_request_success&#x27;: &#x27;0&#x27;, &#x27;arp_failed_item_handles&#x27;: &#x27;{/topology:2/deviceGroup:1/ethernet:1/ipv4:1/item:1}&#x27;}}
Applying traffic 4
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Running traffic 4
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Stopping traffic 4
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Again Applying traffic 3
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Again Running traffic 3
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Again Stopping traffic 3
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
resetting traffic items
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Destroying topology 1
ixiangpf:info: [01/10/2021 23:02:31    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Destroying topology 2
ixiangpf:info: [01/10/2021 23:02:31    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Resetting traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Creating topology 1
ixiangpf:info: [01/10/2021 23:02:31    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;topology_handle&#x27;: &#x27;/topology:1&#x27;}
creating device group 1
ixiangpf:info: [01/10/2021 23:02:31    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;device_group_handle&#x27;: &#x27;/topology:1/deviceGroup:1&#x27;}
creating interface - eth and ip 1
ixiangpf:info: [01/10/2021 23:02:31    info] COMPLETED: interface_config               : PASS
Interface_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;ethernet_handle&#x27;: &#x27;/topology:1/deviceGroup:1/ethernet:1&#x27;, &#x27;ipv6_handle&#x27;: &#x27;/topology:1/deviceGroup:1/ethernet:1/ipv6:1&#x27;, &#x27;interface_handle&#x27;: &#x27;/topology:1/deviceGroup:1/ethernet:1/ipv6:1/item:1 /topology:1/deviceGroup:1/ethernet:1/item:1&#x27;}
starting device group 1
ixiangpf:info: [01/10/2021 23:02:31    info] COMPLETED: test_control                   : PASS
Test_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
creating bgp stack for topology 1
ixiangpf:info: [01/10/2021 23:02:41 warning] Argument: -remote_ipv6_addr is ignored when -handle is: /topology:1/deviceGroup:1/ethernet:1/ipv6:1/item:1
ixiangpf:info: [01/10/2021 23:02:42    info] COMPLETED: emulation_bgp_config           : PASS
Emulation_Bgp_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;bgp_handle&#x27;: &#x27;/topology:1/deviceGroup:1/ethernet:1/ipv6:1/bgpIpv6Peer:1&#x27;}
Stopping device group 1
ixiangpf:info: [01/10/2021 23:02:42    info] COMPLETED: test_control                   : PASS
Test_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
getting protocol info
configuring bgp routes for topology 1
ixiangpf:info: [01/10/2021 23:03:12    info] COMPLETED: emulation_bgp_route_config     : PASS
Emulation_Bgp_Route_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;network_group_handle&#x27;: &#x27;/topology:1/deviceGroup:1/networkGroup:1&#x27;, &#x27;macpool_ip_prefix&#x27;: &#x27;/topology:1/deviceGroup:1/networkGroup:1/ipv6PrefixPools:1&#x27;, &#x27;ip_routes&#x27;: &#x27;/topology:1/deviceGroup:1/networkGroup:1/ipv6PrefixPools:1/bgpV6IPRouteProperty:2&#x27;, &#x27;bgp_routes&#x27;: &#x27;/topology:1/deviceGroup:1/networkGroup:1/ipv6PrefixPools:1/bgpV6IPRouteProperty:2/item:1&#x27;}
Resetting traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Creating topology 2
ixiangpf:info: [01/10/2021 23:03:42    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;topology_handle&#x27;: &#x27;/topology:2&#x27;}
creating device group 2
ixiangpf:info: [01/10/2021 23:03:42    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;device_group_handle&#x27;: &#x27;/topology:2/deviceGroup:1&#x27;}
creating interface - eth and ip 2
ixiangpf:info: [01/10/2021 23:03:42    info] COMPLETED: interface_config               : PASS
Interface_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;ethernet_handle&#x27;: &#x27;/topology:2/deviceGroup:1/ethernet:1&#x27;, &#x27;ipv4_handle&#x27;: &#x27;/topology:2/deviceGroup:1/ethernet:1/ipv4:1&#x27;, &#x27;interface_handle&#x27;: &#x27;/topology:2/deviceGroup:1/ethernet:1/ipv4:1/item:1 /topology:2/deviceGroup:1/ethernet:1/item:1&#x27;}
starting protocols
ixiangpf:info: [01/10/2021 23:03:42    info] COMPLETED: test_control                   : PASS
Test_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
creating bgp for topology 2
ixiangpf:info: [01/10/2021 23:03:53 warning] Argument: -remote_ip_addr is ignored when -handle is: /topology:2/deviceGroup:1/ethernet:1/ipv4:1/item:1
ixiangpf:info: [01/10/2021 23:03:53    info] COMPLETED: emulation_bgp_config           : PASS
Emulation_Bgp_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;bgp_handle&#x27;: &#x27;/topology:2/deviceGroup:1/ethernet:1/ipv4:1/bgpIpv4Peer:1&#x27;}
Stopping device group 2
ixiangpf:info: [01/10/2021 23:03:53    info] COMPLETED: test_control                   : PASS
Test_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
getting protocol info
adding routes for bgp in topology 2
ixiangpf:info: [01/10/2021 23:03:53    info] COMPLETED: emulation_bgp_route_config     : PASS
Emulation_Bgp_Route_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;network_group_handle&#x27;: &#x27;/topology:2/deviceGroup:1/networkGroup:1&#x27;, &#x27;macpool_ip_prefix&#x27;: &#x27;/topology:2/deviceGroup:1/networkGroup:1/ipv4PrefixPools:1&#x27;, &#x27;ip_routes&#x27;: &#x27;/topology:2/deviceGroup:1/networkGroup:1/ipv4PrefixPools:1/bgpIPRouteProperty:2&#x27;, &#x27;bgp_routes&#x27;: &#x27;/topology:2/deviceGroup:1/networkGroup:1/ipv4PrefixPools:1/bgpIPRouteProperty:2/item:1&#x27;}
Stopping all protocols
ixiangpf:info: [01/10/2021 23:04:13    info] COMPLETED: test_control                   : PASS
Test_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Destroying topology 1
ixiangpf:info: [01/10/2021 23:04:13    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Destroying topology 2
ixiangpf:info: [01/10/2021 23:04:13    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Resetting traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Creating topology 1
ixiangpf:info: [01/10/2021 23:04:14    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;topology_handle&#x27;: &#x27;/topology:1&#x27;}
creating device group 1
ixiangpf:info: [01/10/2021 23:04:14    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;device_group_handle&#x27;: &#x27;/topology:1/deviceGroup:1&#x27;}
creating interface - eth and ip 1
ixiangpf:info: [01/10/2021 23:04:14    info] COMPLETED: interface_config               : PASS
Interface_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;ethernet_handle&#x27;: &#x27;/topology:1/deviceGroup:1/ethernet:1&#x27;, &#x27;ipv6_handle&#x27;: &#x27;/topology:1/deviceGroup:1/ethernet:1/ipv6:1&#x27;, &#x27;interface_handle&#x27;: &#x27;/topology:1/deviceGroup:1/ethernet:1/ipv6:1/item:1 /topology:1/deviceGroup:1/ethernet:1/item:1&#x27;}
starting device group 1
ixiangpf:info: [01/10/2021 23:04:14    info] COMPLETED: test_control                   : PASS
Test_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Creating topology 2
ixiangpf:info: [01/10/2021 23:04:14    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;topology_handle&#x27;: &#x27;/topology:2&#x27;}
creating device group 2
ixiangpf:info: [01/10/2021 23:04:14    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;device_group_handle&#x27;: &#x27;/topology:2/deviceGroup:1&#x27;}
creating interface - eth and ip 2
ixiangpf:info: [01/10/2021 23:04:14    info] COMPLETED: interface_config               : PASS
Interface_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;ethernet_handle&#x27;: &#x27;/topology:2/deviceGroup:1/ethernet:1&#x27;, &#x27;ipv6_handle&#x27;: &#x27;/topology:2/deviceGroup:1/ethernet:1/ipv6:1&#x27;, &#x27;interface_handle&#x27;: &#x27;/topology:2/deviceGroup:1/ethernet:1/ipv6:1/item:1 /topology:2/deviceGroup:1/ethernet:1/item:1&#x27;}
starting device group 2
ixiangpf:info: [01/10/2021 23:04:14    info] COMPLETED: test_control                   : PASS
Test_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
creating bgp stack for topology 1
ixiangpf:info: [01/10/2021 23:04:24 warning] Argument: -remote_ipv6_addr is ignored when -handle is: /topology:1/deviceGroup:1/ethernet:1/ipv6:1/item:1
ixiangpf:info: [01/10/2021 23:04:25    info] COMPLETED: emulation_bgp_config           : PASS
Emulation_Bgp_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;bgp_handle&#x27;: &#x27;/topology:1/deviceGroup:1/ethernet:1/ipv6:1/bgpIpv6Peer:1&#x27;}
Stopping device group 1
ixiangpf:info: [01/10/2021 23:04:25    info] COMPLETED: test_control                   : PASS
Test_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
getting protocol info
configuring bgp routes for topology 1
ixiangpf:info: [01/10/2021 23:04:45    info] COMPLETED: emulation_bgp_route_config     : PASS
Emulation_Bgp_Route_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;network_group_handle&#x27;: &#x27;/topology:1/deviceGroup:1/networkGroup:1&#x27;, &#x27;macpool_ip_prefix&#x27;: &#x27;/topology:1/deviceGroup:1/networkGroup:1/ipv6PrefixPools:1&#x27;, &#x27;ip_routes&#x27;: &#x27;/topology:1/deviceGroup:1/networkGroup:1/ipv6PrefixPools:1/bgpV6IPRouteProperty:2&#x27;, &#x27;bgp_routes&#x27;: &#x27;/topology:1/deviceGroup:1/networkGroup:1/ipv6PrefixPools:1/bgpV6IPRouteProperty:2/item:1&#x27;}
Test Completed!!
<br/></div></td></tr></tbody>
      <tbody class="passed results-table-row">
        <tr>
          <td class="col-result">Passed</td>
          <td class="col-name">stats_tests/test_ports_stats.py::test_port_stats</td>
          <td class="col-duration">38.05</td>
          <td class="col-links"></td></tr>
        <tr>
          <td class="extra" colspan="4">
            <div class="log"> -----------------------------Captured stdout setup------------------------------ <br/>ixiatcl:info: Tcl version: 8.6.6
otg(username=None, password=None, api_server=&#x27;10.39.47.41:8888&#x27;, chassis=&#x27;10.39.35.12&#x27;, ports=[&#x27;2/13&#x27;, &#x27;2/14&#x27;, &#x27;2/15&#x27;, &#x27;2/16&#x27;])
{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
<br/> ------------------------------Captured stdout call------------------------------ <br/>{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
[&#x27;1/2/13&#x27;, &#x27;1/2/14&#x27;, &#x27;1/2/15&#x27;, &#x27;1/2/16&#x27;]
fetching stats for first port
Traffic_Stats PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;measure_mode&#x27;: &#x27;mixed&#x27;, &#x27;waiting_for_stats&#x27;: &#x27;1&#x27;, &#x27;aggregate&#x27;: {&#x27;rx&#x27;: {&#x27;pkt_count&#x27;: {&#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;}, &#x27;pkt_rate&#x27;: {&#x27;avg&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;}, &#x27;uds2_frame_rate&#x27;: {&#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;min&#x27;: &#x27;0&#x27;}, &#x27;pkt_kbit_rate&#x27;: {&#x27;avg&#x27;: &#x27;0.000&#x27;, &#x27;max&#x27;: &#x27;0.000&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;min&#x27;: &#x27;0.000&#x27;, &#x27;sum&#x27;: &#x27;0.000&#x27;}, &#x27;raw_pkt_rate&#x27;: {&#x27;max&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;}, &#x27;data_int_errors_count&#x27;: {&#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;}, &#x27;oversize_rate_count&#x27;: {&#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;}, &#x27;rs_fec_uncorrected_error_count&#x27;: {&#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;uds3_frame_rate&#x27;: {&#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;total_pkts&#x27;: {&#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;}, &#x27;control_frames&#x27;: {&#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;}, &#x27;uds5_frame_count&#x27;: {&#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;}, &#x27;rx_aal5_frames_count&#x27;: {&#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;}, &#x27;total_pkt_rate&#x27;: {&#x27;sum&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;}, &#x27;uds2_frame_count&#x27;: {&#x27;min&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;}, &#x27;misdirected_packet_count&#x27;: {&#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;}, &#x27;uds4_frame_count&#x27;: {&#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;}, &#x27;rs_fec_corrected_error_count&#x27;: {&#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;oversize_crc_errors_count&#x27;: {&#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;}, &#x27;uds6_frame_count&#x27;: {&#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;}, &#x27;rx_atm_cells_rate&#x27;: {&#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;oversize_crc_errors_rate_count&#x27;: {&#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;}, &#x27;rs_fec_uncorrected_error_count_rate&#x27;: {&#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;}, &#x27;uds1_frame_rate&#x27;: {&#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;}, &#x27;pkt_bit_rate&#x27;: {&#x27;avg&#x27;: &#x27;0.000&#x27;, &#x27;max&#x27;: &#x27;0.000&#x27;, &#x27;min&#x27;: &#x27;0.000&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0.000&#x27;}, &#x27;rs_fec_corrected_error_count_rate&#x27;: {&#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;pkt_mbit_rate&#x27;: {&#x27;min&#x27;: &#x27;0.000&#x27;, &#x27;sum&#x27;: &#x27;0.000&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;avg&#x27;: &#x27;0.000&#x27;, &#x27;max&#x27;: &#x27;0.000&#x27;}, &#x27;uds4_frame_rate&#x27;: {&#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;}, &#x27;rx_atm_cells_count&#x27;: {&#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;}, &#x27;rx_aal5_frames_rate&#x27;: {&#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;collisions_count&#x27;: {&#x27;min&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;}, &#x27;raw_pkt_count&#x27;: {&#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;}, &#x27;crc_errors&#x27;: {&#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;}, &#x27;uds5_frame_rate&#x27;: {&#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;}, &#x27;pkt_byte_count&#x27;: {&#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;}, &#x27;uds6_frame_rate&#x27;: {&#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;uds1_frame_count&#x27;: {&#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;}, &#x27;uds3_frame_count&#x27;: {&#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;}, &#x27;data_int_frames_count&#x27;: {&#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;}, &#x27;pkt_byte_rate&#x27;: {&#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;}, &#x27;oversize_count&#x27;: {&#x27;avg&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;}}, &#x27;tx&#x27;: {&#x27;pkt_byte_rate&#x27;: {&#x27;avg&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;}, &#x27;pkt_count&#x27;: {&#x27;sum&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;}, &#x27;tx_aal5_scheduled_frames_count&#x27;: {&#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;}, &#x27;tx_aal5_bytes_count&#x27;: {&#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;total_pkts&#x27;: {&#x27;count&#x27;: &#x27;1&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;}, &#x27;elapsed_time&#x27;: {&#x27;sum&#x27;: &#x27;979970760&#x27;, &#x27;avg&#x27;: &#x27;979970760&#x27;, &#x27;max&#x27;: &#x27;979970760&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;min&#x27;: &#x27;979970760&#x27;}, &#x27;total_pkt_rate&#x27;: {&#x27;min&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;}, &#x27;pkt_rate&#x27;: {&#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;}, &#x27;scheduled_pkt_count&#x27;: {&#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;}, &#x27;tx_aal5_scheduled_cells_count&#x27;: {&#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;pkt_mbit_rate&#x27;: {&#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0.000&#x27;, &#x27;avg&#x27;: &#x27;0.000&#x27;, &#x27;max&#x27;: &#x27;0.000&#x27;, &#x27;min&#x27;: &#x27;0.000&#x27;}, &#x27;pkt_kbit_rate&#x27;: {&#x27;min&#x27;: &#x27;0.000&#x27;, &#x27;sum&#x27;: &#x27;0.000&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;avg&#x27;: &#x27;0.000&#x27;, &#x27;max&#x27;: &#x27;0.000&#x27;}, &#x27;tx_aal5_frames_count&#x27;: {&#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;tx_atm_cells_rate&#x27;: {&#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;}, &#x27;scheduled_pkt_rate&#x27;: {&#x27;max&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;}, &#x27;tx_aal5_scheduled_frames_rate&#x27;: {&#x27;min&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;}, &#x27;pkt_bit_rate&#x27;: {&#x27;min&#x27;: &#x27;0.000&#x27;, &#x27;sum&#x27;: &#x27;0.000&#x27;, &#x27;avg&#x27;: &#x27;0.000&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;max&#x27;: &#x27;0.000&#x27;}, &#x27;pkt_byte_count&#x27;: {&#x27;min&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;}, &#x27;raw_pkt_count&#x27;: {&#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;}, &#x27;tx_aal5_bytes_rate&#x27;: {&#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;control_frames&#x27;: {&#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;}, &#x27;tx_aal5_scheduled_cells_rate&#x27;: {&#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;}, &#x27;tx_aal5_frames_rate&#x27;: {&#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;}, &#x27;tx_atm_cells_count&#x27;: {&#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;}, &#x27;line_speed&#x27;: {&#x27;count&#x27;: &#x27;1&#x27;}}, &#x27;duplex_mode&#x27;: {&#x27;count&#x27;: &#x27;1&#x27;}, &#x27;port_name&#x27;: {&#x27;count&#x27;: &#x27;1&#x27;}}, &#x27;1/2/13&#x27;: {&#x27;aggregate&#x27;: {&#x27;rx&#x27;: {&#x27;total_pkts&#x27;: &#x27;0&#x27;, &#x27;oversize_count&#x27;: &#x27;0&#x27;, &#x27;data_int_errors_count&#x27;: &#x27;0&#x27;, &#x27;raw_pkt_count&#x27;: &#x27;0&#x27;, &#x27;pkt_rate&#x27;: &#x27;0&#x27;, &#x27;oversize_crc_errors_count&#x27;: &#x27;N/A&#x27;, &#x27;uds1_frame_rate&#x27;: &#x27;0&#x27;, &#x27;pkt_bit_count&#x27;: &#x27;N/A&#x27;, &#x27;uds2_frame_rate&#x27;: &#x27;0&#x27;, &#x27;raw_pkt_rate&#x27;: &#x27;0&#x27;, &#x27;rx_aal5_frames_rate&#x27;: &#x27;N/A&#x27;, &#x27;oversize_crc_errors_rate_count&#x27;: &#x27;N/A&#x27;, &#x27;oversize_rate_count&#x27;: &#x27;0&#x27;, &#x27;crc_errors&#x27;: &#x27;0&#x27;, &#x27;uds3_frame_rate&#x27;: &#x27;N/A&#x27;, &#x27;uds6_frame_count&#x27;: &#x27;N/A&#x27;, &#x27;control_frames&#x27;: &#x27;0&#x27;, &#x27;pkt_bit_rate&#x27;: &#x27;0.000&#x27;, &#x27;rs_fec_uncorrected_error_count_rate&#x27;: &#x27;N/A&#x27;, &#x27;uds4_frame_rate&#x27;: &#x27;N/A&#x27;, &#x27;rx_atm_cells_rate&#x27;: &#x27;N/A&#x27;, &#x27;rx_aal5_frames_count&#x27;: &#x27;N/A&#x27;, &#x27;pkt_byte_count&#x27;: &#x27;0&#x27;, &#x27;total_pkt_rate&#x27;: &#x27;0&#x27;, &#x27;pkt_kbit_rate&#x27;: &#x27;0.000&#x27;, &#x27;uds5_frame_count&#x27;: &#x27;N/A&#x27;, &#x27;pkt_byte_rate&#x27;: &#x27;0&#x27;, &#x27;uds5_frame_rate&#x27;: &#x27;N/A&#x27;, &#x27;collisions_count&#x27;: &#x27;0&#x27;, &#x27;uds4_frame_count&#x27;: &#x27;N/A&#x27;, &#x27;uds6_frame_rate&#x27;: &#x27;N/A&#x27;, &#x27;rx_atm_cells_count&#x27;: &#x27;N/A&#x27;, &#x27;data_int_frames_count&#x27;: &#x27;0&#x27;, &#x27;uds3_frame_count&#x27;: &#x27;N/A&#x27;, &#x27;rs_fec_corrected_error_count&#x27;: &#x27;N/A&#x27;, &#x27;misdirected_packet_count&#x27;: &#x27;0&#x27;, &#x27;rs_fec_uncorrected_error_count&#x27;: &#x27;N/A&#x27;, &#x27;rs_fec_corrected_error_count_rate&#x27;: &#x27;N/A&#x27;, &#x27;uds2_frame_count&#x27;: &#x27;0&#x27;, &#x27;pkt_count&#x27;: &#x27;0&#x27;, &#x27;uds1_frame_count&#x27;: &#x27;0&#x27;, &#x27;pkt_mbit_rate&#x27;: &#x27;0.000&#x27;}, &#x27;tx&#x27;: {&#x27;tx_aal5_scheduled_frames_count&#x27;: &#x27;0&#x27;, &#x27;tx_atm_cells_rate&#x27;: &#x27;N/A&#x27;, &#x27;tx_aal5_bytes_count&#x27;: &#x27;N/A&#x27;, &#x27;pkt_count&#x27;: &#x27;0&#x27;, &#x27;tx_aal5_scheduled_cells_rate&#x27;: &#x27;N/A&#x27;, &#x27;tx_aal5_frames_rate&#x27;: &#x27;N/A&#x27;, &#x27;pkt_rate&#x27;: &#x27;0&#x27;, &#x27;control_frames&#x27;: &#x27;0&#x27;, &#x27;pkt_mbit_rate&#x27;: &#x27;0.000&#x27;, &#x27;pkt_byte_count&#x27;: &#x27;0&#x27;, &#x27;total_pkt_rate&#x27;: &#x27;0&#x27;, &#x27;line_speed&#x27;: &#x27;1000 Mbps&#x27;, &#x27;scheduled_pkt_rate&#x27;: &#x27;0&#x27;, &#x27;raw_pkt_count&#x27;: &#x27;0&#x27;, &#x27;pkt_bit_count&#x27;: &#x27;N/A&#x27;, &#x27;tx_aal5_scheduled_frames_rate&#x27;: &#x27;0&#x27;, &#x27;tx_aal5_bytes_rate&#x27;: &#x27;N/A&#x27;, &#x27;tx_aal5_scheduled_cells_count&#x27;: &#x27;N/A&#x27;, &#x27;scheduled_pkt_count&#x27;: &#x27;0&#x27;, &#x27;pkt_bit_rate&#x27;: &#x27;0.000&#x27;, &#x27;elapsed_time&#x27;: &#x27;979970760&#x27;, &#x27;total_pkts&#x27;: &#x27;0&#x27;, &#x27;pkt_kbit_rate&#x27;: &#x27;0.000&#x27;, &#x27;pkt_byte_rate&#x27;: &#x27;0&#x27;, &#x27;tx_aal5_frames_count&#x27;: &#x27;N/A&#x27;, &#x27;tx_atm_cells_count&#x27;: &#x27;N/A&#x27;}, &#x27;duplex_mode&#x27;: &#x27;Full&#x27;, &#x27;port_name&#x27;: &#x27;1/2/13&#x27;}}}
fetching stats for second port
Traffic_Stats PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;measure_mode&#x27;: &#x27;mixed&#x27;, &#x27;waiting_for_stats&#x27;: &#x27;1&#x27;, &#x27;aggregate&#x27;: {&#x27;rx&#x27;: {&#x27;pkt_count&#x27;: {&#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;}, &#x27;pkt_rate&#x27;: {&#x27;avg&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;}, &#x27;uds2_frame_rate&#x27;: {&#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;min&#x27;: &#x27;0&#x27;}, &#x27;pkt_kbit_rate&#x27;: {&#x27;avg&#x27;: &#x27;0.000&#x27;, &#x27;max&#x27;: &#x27;0.000&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;min&#x27;: &#x27;0.000&#x27;, &#x27;sum&#x27;: &#x27;0.000&#x27;}, &#x27;raw_pkt_rate&#x27;: {&#x27;max&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;}, &#x27;data_int_errors_count&#x27;: {&#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;}, &#x27;oversize_rate_count&#x27;: {&#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;}, &#x27;rs_fec_uncorrected_error_count&#x27;: {&#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;uds3_frame_rate&#x27;: {&#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;total_pkts&#x27;: {&#x27;max&#x27;: &#x27;281&#x27;, &#x27;min&#x27;: &#x27;281&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;281&#x27;, &#x27;avg&#x27;: &#x27;281&#x27;}, &#x27;control_frames&#x27;: {&#x27;max&#x27;: &#x27;16&#x27;, &#x27;min&#x27;: &#x27;16&#x27;, &#x27;sum&#x27;: &#x27;16&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;avg&#x27;: &#x27;16&#x27;}, &#x27;uds5_frame_count&#x27;: {&#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;}, &#x27;rx_aal5_frames_count&#x27;: {&#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;}, &#x27;total_pkt_rate&#x27;: {&#x27;sum&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;}, &#x27;uds2_frame_count&#x27;: {&#x27;min&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;}, &#x27;misdirected_packet_count&#x27;: {&#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;}, &#x27;uds4_frame_count&#x27;: {&#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;}, &#x27;rs_fec_corrected_error_count&#x27;: {&#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;oversize_crc_errors_count&#x27;: {&#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;}, &#x27;uds6_frame_count&#x27;: {&#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;}, &#x27;rx_atm_cells_rate&#x27;: {&#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;oversize_crc_errors_rate_count&#x27;: {&#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;}, &#x27;rs_fec_uncorrected_error_count_rate&#x27;: {&#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;}, &#x27;uds1_frame_rate&#x27;: {&#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;}, &#x27;pkt_bit_rate&#x27;: {&#x27;avg&#x27;: &#x27;0.000&#x27;, &#x27;max&#x27;: &#x27;0.000&#x27;, &#x27;min&#x27;: &#x27;0.000&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0.000&#x27;}, &#x27;rs_fec_corrected_error_count_rate&#x27;: {&#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;pkt_mbit_rate&#x27;: {&#x27;min&#x27;: &#x27;0.000&#x27;, &#x27;sum&#x27;: &#x27;0.000&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;avg&#x27;: &#x27;0.000&#x27;, &#x27;max&#x27;: &#x27;0.000&#x27;}, &#x27;uds4_frame_rate&#x27;: {&#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;}, &#x27;rx_atm_cells_count&#x27;: {&#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;}, &#x27;rx_aal5_frames_rate&#x27;: {&#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;collisions_count&#x27;: {&#x27;min&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;}, &#x27;raw_pkt_count&#x27;: {&#x27;min&#x27;: &#x27;281&#x27;, &#x27;sum&#x27;: &#x27;281&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;avg&#x27;: &#x27;281&#x27;, &#x27;max&#x27;: &#x27;281&#x27;}, &#x27;crc_errors&#x27;: {&#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;}, &#x27;uds5_frame_rate&#x27;: {&#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;}, &#x27;pkt_byte_count&#x27;: {&#x27;sum&#x27;: &#x27;18462&#x27;, &#x27;avg&#x27;: &#x27;18462&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;max&#x27;: &#x27;18462&#x27;, &#x27;min&#x27;: &#x27;18462&#x27;}, &#x27;uds6_frame_rate&#x27;: {&#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;uds1_frame_count&#x27;: {&#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;}, &#x27;uds3_frame_count&#x27;: {&#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;}, &#x27;data_int_frames_count&#x27;: {&#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;}, &#x27;pkt_byte_rate&#x27;: {&#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;}, &#x27;oversize_count&#x27;: {&#x27;avg&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;}}, &#x27;tx&#x27;: {&#x27;pkt_byte_rate&#x27;: {&#x27;avg&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;}, &#x27;pkt_count&#x27;: {&#x27;sum&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;}, &#x27;tx_aal5_scheduled_frames_count&#x27;: {&#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;}, &#x27;tx_aal5_bytes_count&#x27;: {&#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;total_pkts&#x27;: {&#x27;count&#x27;: &#x27;1&#x27;, &#x27;max&#x27;: &#x27;20&#x27;, &#x27;min&#x27;: &#x27;20&#x27;, &#x27;sum&#x27;: &#x27;20&#x27;, &#x27;avg&#x27;: &#x27;20&#x27;}, &#x27;elapsed_time&#x27;: {&#x27;sum&#x27;: &#x27;12603931260&#x27;, &#x27;avg&#x27;: &#x27;12603931260&#x27;, &#x27;max&#x27;: &#x27;12603931260&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;min&#x27;: &#x27;12603931260&#x27;}, &#x27;total_pkt_rate&#x27;: {&#x27;min&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;}, &#x27;pkt_rate&#x27;: {&#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;min&#x27;: &#x27;0&#x27;}, &#x27;scheduled_pkt_count&#x27;: {&#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;}, &#x27;tx_aal5_scheduled_cells_count&#x27;: {&#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;pkt_mbit_rate&#x27;: {&#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0.000&#x27;, &#x27;avg&#x27;: &#x27;0.000&#x27;, &#x27;max&#x27;: &#x27;0.000&#x27;, &#x27;min&#x27;: &#x27;0.000&#x27;}, &#x27;pkt_kbit_rate&#x27;: {&#x27;min&#x27;: &#x27;0.000&#x27;, &#x27;sum&#x27;: &#x27;0.000&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;avg&#x27;: &#x27;0.000&#x27;, &#x27;max&#x27;: &#x27;0.000&#x27;}, &#x27;tx_aal5_frames_count&#x27;: {&#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;tx_atm_cells_rate&#x27;: {&#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;}, &#x27;scheduled_pkt_rate&#x27;: {&#x27;max&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;min&#x27;: &#x27;0&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;}, &#x27;tx_aal5_scheduled_frames_rate&#x27;: {&#x27;min&#x27;: &#x27;0&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;0&#x27;, &#x27;avg&#x27;: &#x27;0&#x27;, &#x27;max&#x27;: &#x27;0&#x27;}, &#x27;pkt_bit_rate&#x27;: {&#x27;min&#x27;: &#x27;0.000&#x27;, &#x27;sum&#x27;: &#x27;0.000&#x27;, &#x27;avg&#x27;: &#x27;0.000&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;max&#x27;: &#x27;0.000&#x27;}, &#x27;pkt_byte_count&#x27;: {&#x27;min&#x27;: &#x27;1476&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;1476&#x27;, &#x27;avg&#x27;: &#x27;1476&#x27;, &#x27;max&#x27;: &#x27;1476&#x27;}, &#x27;raw_pkt_count&#x27;: {&#x27;sum&#x27;: &#x27;20&#x27;, &#x27;avg&#x27;: &#x27;20&#x27;, &#x27;max&#x27;: &#x27;20&#x27;, &#x27;min&#x27;: &#x27;20&#x27;, &#x27;count&#x27;: &#x27;1&#x27;}, &#x27;tx_aal5_bytes_rate&#x27;: {&#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;, &#x27;sum&#x27;: &#x27;N/A&#x27;}, &#x27;control_frames&#x27;: {&#x27;avg&#x27;: &#x27;20&#x27;, &#x27;max&#x27;: &#x27;20&#x27;, &#x27;min&#x27;: &#x27;20&#x27;, &#x27;count&#x27;: &#x27;1&#x27;, &#x27;sum&#x27;: &#x27;20&#x27;}, &#x27;tx_aal5_scheduled_cells_rate&#x27;: {&#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;}, &#x27;tx_aal5_frames_rate&#x27;: {&#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;}, &#x27;tx_atm_cells_count&#x27;: {&#x27;sum&#x27;: &#x27;N/A&#x27;, &#x27;avg&#x27;: &#x27;N/A&#x27;, &#x27;max&#x27;: &#x27;N/A&#x27;, &#x27;count&#x27;: &#x27;N/A&#x27;, &#x27;min&#x27;: &#x27;N/A&#x27;}, &#x27;line_speed&#x27;: {&#x27;count&#x27;: &#x27;1&#x27;}}, &#x27;duplex_mode&#x27;: {&#x27;count&#x27;: &#x27;1&#x27;}, &#x27;port_name&#x27;: {&#x27;count&#x27;: &#x27;1&#x27;}}, &#x27;1/2/14&#x27;: {&#x27;aggregate&#x27;: {&#x27;rx&#x27;: {&#x27;pkt_byte_rate&#x27;: &#x27;0&#x27;, &#x27;uds5_frame_count&#x27;: &#x27;N/A&#x27;, &#x27;oversize_crc_errors_rate_count&#x27;: &#x27;N/A&#x27;, &#x27;collisions_count&#x27;: &#x27;0&#x27;, &#x27;uds4_frame_count&#x27;: &#x27;N/A&#x27;, &#x27;raw_pkt_rate&#x27;: &#x27;0&#x27;, &#x27;rx_aal5_frames_rate&#x27;: &#x27;N/A&#x27;, &#x27;rs_fec_corrected_error_count&#x27;: &#x27;N/A&#x27;, &#x27;oversize_rate_count&#x27;: &#x27;0&#x27;, &#x27;uds3_frame_count&#x27;: &#x27;N/A&#x27;, &#x27;pkt_bit_rate&#x27;: &#x27;0.000&#x27;, &#x27;oversize_count&#x27;: &#x27;0&#x27;, &#x27;uds2_frame_count&#x27;: &#x27;0&#x27;, &#x27;uds1_frame_rate&#x27;: &#x27;0&#x27;, &#x27;rs_fec_corrected_error_count_rate&#x27;: &#x27;N/A&#x27;, &#x27;data_int_frames_count&#x27;: &#x27;0&#x27;, &#x27;pkt_rate&#x27;: &#x27;0&#x27;, &#x27;pkt_mbit_rate&#x27;: &#x27;0.000&#x27;, &#x27;oversize_crc_errors_count&#x27;: &#x27;N/A&#x27;, &#x27;uds2_frame_rate&#x27;: &#x27;0&#x27;, &#x27;uds1_frame_count&#x27;: &#x27;0&#x27;, &#x27;rx_atm_cells_rate&#x27;: &#x27;N/A&#x27;, &#x27;rx_atm_cells_count&#x27;: &#x27;N/A&#x27;, &#x27;rs_fec_uncorrected_error_count&#x27;: &#x27;N/A&#x27;, &#x27;raw_pkt_count&#x27;: &#x27;281&#x27;, &#x27;uds3_frame_rate&#x27;: &#x27;N/A&#x27;, &#x27;pkt_bit_count&#x27;: &#x27;N/A&#x27;, &#x27;control_frames&#x27;: &#x27;16&#x27;, &#x27;rx_aal5_frames_count&#x27;: &#x27;N/A&#x27;, &#x27;misdirected_packet_count&#x27;: &#x27;0&#x27;, &#x27;pkt_byte_count&#x27;: &#x27;18462&#x27;, &#x27;total_pkt_rate&#x27;: &#x27;0&#x27;, &#x27;uds4_frame_rate&#x27;: &#x27;N/A&#x27;, &#x27;total_pkts&#x27;: &#x27;281&#x27;, &#x27;rs_fec_uncorrected_error_count_rate&#x27;: &#x27;N/A&#x27;, &#x27;uds5_frame_rate&#x27;: &#x27;N/A&#x27;, &#x27;pkt_count&#x27;: &#x27;0&#x27;, &#x27;data_int_errors_count&#x27;: &#x27;0&#x27;, &#x27;uds6_frame_rate&#x27;: &#x27;N/A&#x27;, &#x27;uds6_frame_count&#x27;: &#x27;N/A&#x27;, &#x27;pkt_kbit_rate&#x27;: &#x27;0.000&#x27;, &#x27;crc_errors&#x27;: &#x27;0&#x27;}, &#x27;tx&#x27;: {&#x27;pkt_count&#x27;: &#x27;0&#x27;, &#x27;raw_pkt_count&#x27;: &#x27;20&#x27;, &#x27;tx_aal5_bytes_count&#x27;: &#x27;N/A&#x27;, &#x27;pkt_bit_count&#x27;: &#x27;N/A&#x27;, &#x27;line_speed&#x27;: &#x27;1000 Mbps&#x27;, &#x27;tx_aal5_frames_rate&#x27;: &#x27;N/A&#x27;, &#x27;tx_aal5_frames_count&#x27;: &#x27;N/A&#x27;, &#x27;tx_atm_cells_rate&#x27;: &#x27;N/A&#x27;, &#x27;pkt_kbit_rate&#x27;: &#x27;0.000&#x27;, &#x27;scheduled_pkt_rate&#x27;: &#x27;0&#x27;, &#x27;pkt_byte_rate&#x27;: &#x27;0&#x27;, &#x27;tx_aal5_bytes_rate&#x27;: &#x27;N/A&#x27;, &#x27;total_pkts&#x27;: &#x27;20&#x27;, &#x27;tx_aal5_scheduled_frames_rate&#x27;: &#x27;0&#x27;, &#x27;pkt_rate&#x27;: &#x27;0&#x27;, &#x27;scheduled_pkt_count&#x27;: &#x27;0&#x27;, &#x27;tx_aal5_scheduled_cells_count&#x27;: &#x27;N/A&#x27;, &#x27;control_frames&#x27;: &#x27;20&#x27;, &#x27;tx_aal5_scheduled_cells_rate&#x27;: &#x27;N/A&#x27;, &#x27;pkt_bit_rate&#x27;: &#x27;0.000&#x27;, &#x27;pkt_byte_count&#x27;: &#x27;1476&#x27;, &#x27;total_pkt_rate&#x27;: &#x27;0&#x27;, &#x27;elapsed_time&#x27;: &#x27;12603931260&#x27;, &#x27;tx_aal5_scheduled_frames_count&#x27;: &#x27;0&#x27;, &#x27;pkt_mbit_rate&#x27;: &#x27;0.000&#x27;, &#x27;tx_atm_cells_count&#x27;: &#x27;N/A&#x27;}, &#x27;port_name&#x27;: &#x27;1/2/14&#x27;, &#x27;duplex_mode&#x27;: &#x27;Full&#x27;}}}
Test completed
<br/></div></td></tr></tbody>
      <tbody class="passed results-table-row">
        <tr>
          <td class="col-result">Passed</td>
          <td class="col-name">traffic_tests/test_continuous_multiple_traffic_items.py::test_continuous_multiple_traffic_items</td>
          <td class="col-duration">86.76</td>
          <td class="col-links"></td></tr>
        <tr>
          <td class="extra" colspan="4">
            <div class="log"> -----------------------------Captured stdout setup------------------------------ <br/>ixiatcl:info: Tcl version: 8.6.6
otg(username=None, password=None, api_server=&#x27;10.39.47.41:8888&#x27;, chassis=&#x27;10.39.35.12&#x27;, ports=[&#x27;2/13&#x27;, &#x27;2/14&#x27;, &#x27;2/15&#x27;, &#x27;2/16&#x27;])
{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
<br/> ------------------------------Captured stdout call------------------------------ <br/>{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
[&#x27;1/2/13&#x27;, &#x27;1/2/14&#x27;, &#x27;1/2/15&#x27;, &#x27;1/2/16&#x27;]
Creating raw traffic
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI0-Traffic_0&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI1-Traffic_1&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:2/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:2/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI2-Traffic_2&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:3/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:3/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI3-Traffic_3&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:4/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:4/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI4-Traffic_4&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:5/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:5/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:5/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:5/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI5-Traffic_5&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:6/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:6/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:6/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:6/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI6-Traffic_6&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:7/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:7/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:7/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:7/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI7-Traffic_7&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:8/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:8/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:8/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:8/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:8/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:8/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:8/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:8/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI8-Traffic_8&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:9/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:9/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:9/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:9/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:9/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:9/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:9/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:9/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI9-Traffic_9&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:10/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:10/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:10/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:10/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:10/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:10/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:10/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:10/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Repeated start operation on all items
Iteration count: 1
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 3.968316078186035
Iteration count: 2
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 1.0268580913543701
Iteration count: 3
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 1.0268590450286865
Iteration count: 4
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 1.0268588066101074
Iteration count: 5
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 1.0275142192840576
Iteration count: 6
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 1.0268583297729492
Iteration count: 7
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 1.0275592803955078
Iteration count: 8
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 1.0268588066101074
Iteration count: 9
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 1.0278596878051758
Iteration count: 10
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 1.0268583297729492
Repeated stop operation on all items
Iteration count: 1
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 3.544860363006592
Iteration count: 2
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 1.0268583297729492
Iteration count: 3
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 1.026857852935791
Iteration count: 4
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 1.0268580913543701
Iteration count: 5
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 1.026857852935791
Iteration count: 6
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 1.0268583297729492
Iteration count: 7
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 1.0268580913543701
Iteration count: 8
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 1.0268588066101074
Iteration count: 9
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 1.0278594493865967
Iteration count: 10
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 1.0268588066101074
test complete!
<br/></div></td></tr></tbody>
      <tbody class="passed results-table-row">
        <tr>
          <td class="col-result">Passed</td>
          <td class="col-name">traffic_tests/test_continuous_single_traffic_item.py::test_continuous_single_traffic_item</td>
          <td class="col-duration">86.03</td>
          <td class="col-links"></td></tr>
        <tr>
          <td class="extra" colspan="4">
            <div class="log"> -----------------------------Captured stdout setup------------------------------ <br/>ixiatcl:info: Tcl version: 8.6.6
otg(username=None, password=None, api_server=&#x27;10.39.47.41:8888&#x27;, chassis=&#x27;10.39.35.12&#x27;, ports=[&#x27;2/13&#x27;, &#x27;2/14&#x27;, &#x27;2/15&#x27;, &#x27;2/16&#x27;])
{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
<br/> ------------------------------Captured stdout call------------------------------ <br/>{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
[&#x27;1/2/13&#x27;, &#x27;1/2/14&#x27;, &#x27;1/2/15&#x27;, &#x27;1/2/16&#x27;]
Creating raw traffic
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI0-Traffic_0&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI1-Traffic_1&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:2/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:2/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI2-Traffic_2&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:3/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:3/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI3-Traffic_3&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:4/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:4/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI4-Traffic_4&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:5/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:5/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:5/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:5/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI5-Traffic_5&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:6/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:6/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:6/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:6/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI6-Traffic_6&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:7/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:7/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:7/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:7/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI7-Traffic_7&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:8/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:8/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:8/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:8/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:8/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:8/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:8/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:8/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI8-Traffic_8&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:9/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:9/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:9/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:9/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:9/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:9/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:9/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:9/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI9-Traffic_9&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:10/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:10/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:10/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:10/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:10/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:10/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:10/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:10/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Repeated start operation on first traffic item
Iteration count: 1
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 3.8317253589630127
Iteration count: 2
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 1.0228548049926758
Iteration count: 3
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 1.022855520248413
Iteration count: 4
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 1.022855281829834
Iteration count: 5
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 1.023857593536377
Iteration count: 6
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 1.022855281829834
Iteration count: 7
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 1.0228548049926758
Iteration count: 8
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 1.0238556861877441
Iteration count: 9
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 1.0238561630249023
Iteration count: 10
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 1.0228545665740967
Repeated stop operation on first traffic item
Iteration count: 1
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 3.641042709350586
Iteration count: 2
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 1.0228548049926758
Iteration count: 3
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 1.022855520248413
Iteration count: 4
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 1.0238561630249023
Iteration count: 5
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 1.0228548049926758
Iteration count: 6
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 1.0839064121246338
Iteration count: 7
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 1.0228550434112549
Iteration count: 8
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 1.0234289169311523
Iteration count: 9
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 1.0228548049926758
Iteration count: 10
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 1.0228550434112549
test complete!
<br/></div></td></tr></tbody>
      <tbody class="passed results-table-row">
        <tr>
          <td class="col-result">Passed</td>
          <td class="col-name">traffic_tests/test_continuous_start_stop_traffic.py::test_continuous_start_stop_traffic</td>
          <td class="col-duration">129.10</td>
          <td class="col-links"></td></tr>
        <tr>
          <td class="extra" colspan="4">
            <div class="log"> -----------------------------Captured stdout setup------------------------------ <br/>ixiatcl:info: Tcl version: 8.6.6
otg(username=None, password=None, api_server=&#x27;10.39.47.41:8888&#x27;, chassis=&#x27;10.39.35.12&#x27;, ports=[&#x27;2/13&#x27;, &#x27;2/14&#x27;, &#x27;2/15&#x27;, &#x27;2/16&#x27;])
{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
<br/> ------------------------------Captured stdout call------------------------------ <br/>{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
[&#x27;1/2/13&#x27;, &#x27;1/2/14&#x27;, &#x27;1/2/15&#x27;, &#x27;1/2/16&#x27;]
Creating raw traffic
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI0-Traffic_0&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI1-Traffic_1&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:2/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:2/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI2-Traffic_2&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:3/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:3/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI3-Traffic_3&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:4/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:4/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI4-Traffic_4&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:5/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:5/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:5/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:5/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI5-Traffic_5&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:6/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:6/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:6/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:6/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI6-Traffic_6&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:7/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:7/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:7/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:7/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI7-Traffic_7&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:8/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:8/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:8/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:8/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:8/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:8/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:8/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:8/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI8-Traffic_8&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:9/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:9/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:9/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:9/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:9/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:9/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:9/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:9/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI9-Traffic_9&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:10/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:10/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:10/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:10/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:10/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:10/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:10/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:10/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Repeated start and stop operation on all items
Iteration count: 1
Starting traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 3.855221748352051
Stopping traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 3.668065309524536
Iteration count: 2
Starting traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 3.3287816047668457
Stopping traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 3.5479650497436523
Iteration count: 3
Starting traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 3.287747621536255
Stopping traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 3.6520516872406006
Iteration count: 4
Starting traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 3.2126848697662354
Stopping traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 3.6478281021118164
Iteration count: 5
Starting traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 3.143627643585205
Stopping traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 3.5429608821868896
Iteration count: 6
Starting traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 3.2317018508911133
Stopping traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 3.1462974548339844
Iteration count: 7
Starting traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 3.211684226989746
Stopping traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 3.668065309524536
Iteration count: 8
Starting traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 3.2116847038269043
Stopping traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 3.1465814113616943
Iteration count: 9
Starting traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 3.205678701400757
Stopping traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 3.6520516872406006
Iteration count: 10
Starting traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 3.1916680335998535
Stopping traffic
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 3.6460468769073486
test complete!
<br/></div></td></tr></tbody>
      <tbody class="passed results-table-row">
        <tr>
          <td class="col-result">Passed</td>
          <td class="col-name">traffic_tests/test_create_traffic_after_topology_deletion.py::test_create_traffic_after_topology_deletion</td>
          <td class="col-duration">29.37</td>
          <td class="col-links"></td></tr>
        <tr>
          <td class="extra" colspan="4">
            <div class="log"> -----------------------------Captured stdout setup------------------------------ <br/>ixiatcl:info: Tcl version: 8.6.6
otg(username=None, password=None, api_server=&#x27;10.39.47.41:8888&#x27;, chassis=&#x27;10.39.35.12&#x27;, ports=[&#x27;2/13&#x27;, &#x27;2/14&#x27;, &#x27;2/15&#x27;, &#x27;2/16&#x27;])
{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
<br/> ------------------------------Captured stdout call------------------------------ <br/>{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
[&#x27;1/2/13&#x27;, &#x27;1/2/14&#x27;, &#x27;1/2/15&#x27;, &#x27;1/2/16&#x27;]
Creating traffic
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI0-HLTAPI_TRAFFICITEM_540&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;vlan-2&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;fcs-3&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;vlan-2&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;fcs-3&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet.VLAN&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI1-HLTAPI_TRAFFICITEM_540&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:2/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:2/configElement:1/stack:&quot;vlan-2&quot; ::ixNet::OBJ-/traffic/trafficItem:2/configElement:1/stack:&quot;fcs-3&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1/stack:&quot;vlan-2&quot; ::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1/stack:&quot;fcs-3&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet.VLAN&#x27;}}
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
ixiangpf:info: [01/10/2021 23:11:38    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;topology_handle&#x27;: &#x27;/topology:1&#x27;}
ixiangpf:info: [01/10/2021 23:11:38    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;device_group_handle&#x27;: &#x27;/topology:1/deviceGroup:1&#x27;}
working
ixiangpf:info: [01/10/2021 23:11:38    info] COMPLETED: interface_config               : PASS
Interface_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;ethernet_handle&#x27;: &#x27;/topology:1/deviceGroup:1/ethernet:1&#x27;, &#x27;ipv4_handle&#x27;: &#x27;/topology:1/deviceGroup:1/ethernet:1/ipv4:1&#x27;, &#x27;interface_handle&#x27;: &#x27;/topology:1/deviceGroup:1/ethernet:1/ipv4:1/item:1 /topology:1/deviceGroup:1/ethernet:1/item:1&#x27;}
ixiangpf:info: [01/10/2021 23:11:38    info] COMPLETED: test_control                   : PASS
Test_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
ixiangpf:info: [01/10/2021 23:11:38    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;topology_handle&#x27;: &#x27;/topology:2&#x27;}
ixiangpf:info: [01/10/2021 23:11:38    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;device_group_handle&#x27;: &#x27;/topology:2/deviceGroup:1&#x27;}
ixiangpf:info: [01/10/2021 23:11:38    info] COMPLETED: interface_config               : PASS
Interface_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;ethernet_handle&#x27;: &#x27;/topology:2/deviceGroup:1/ethernet:1&#x27;, &#x27;ipv4_handle&#x27;: &#x27;/topology:2/deviceGroup:1/ethernet:1/ipv4:1&#x27;, &#x27;interface_handle&#x27;: &#x27;/topology:2/deviceGroup:1/ethernet:1/ipv4:1/item:1 /topology:2/deviceGroup:1/ethernet:1/item:1&#x27;}
ixiangpf:info: [01/10/2021 23:11:38    info] COMPLETED: test_control                   : PASS
Test_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27; ::ixNet::OBJ-/traffic/trafficItem:3 - {Not all the Packets could be Generated: One or more destination MACs or VPNs are invalid or unreachable and the packets configured to be sent to them were not created}.&#x27;, &#x27;stream_id&#x27;: &#x27;TI2-HLTAPI_TRAFFICITEM_540&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:3/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:3/configElement:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:3/configElement:1/stack:&quot;fcs-3&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1/stack:&quot;fcs-3&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet.IPv4&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27; ::ixNet::OBJ-/traffic/trafficItem:4 - {Not all the Packets could be Generated: One or more destination MACs or VPNs are invalid or unreachable and the packets configured to be sent to them were not created}.&#x27;, &#x27;stream_id&#x27;: &#x27;TI3-HLTAPI_TRAFFICITEM_540&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:4/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:4/configElement:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:4/configElement:1/stack:&quot;fcs-3&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1/stack:&quot;fcs-3&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet.IPv4&#x27;}}
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI4-HLTAPI_TRAFFICITEM_540&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:5/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:5/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:5/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:5/configElement:1/stack:&quot;vlan-2&quot; ::ixNet::OBJ-/traffic/trafficItem:5/configElement:1/stack:&quot;fcs-3&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1/stack:&quot;vlan-2&quot; ::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1/stack:&quot;fcs-3&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet.VLAN&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI5-HLTAPI_TRAFFICITEM_540&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:6/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:6/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:6/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:6/configElement:1/stack:&quot;vlan-2&quot; ::ixNet::OBJ-/traffic/trafficItem:6/configElement:1/stack:&quot;fcs-3&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1/stack:&quot;vlan-2&quot; ::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1/stack:&quot;fcs-3&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet.VLAN&#x27;}}
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
ixiangpf:info: [01/10/2021 23:11:42    info] COMPLETED: test_control                   : PASS
Test_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
ixiangpf:info: [01/10/2021 23:11:42    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
ixiangpf:info: [01/10/2021 23:11:42    info] COMPLETED: topology_config                : PASS
Topology_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI6-HLTAPI_TRAFFICITEM_540&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:7/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:7/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:7/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:7/configElement:1/stack:&quot;vlan-2&quot; ::ixNet::OBJ-/traffic/trafficItem:7/configElement:1/stack:&quot;fcs-3&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1/stack:&quot;vlan-2&quot; ::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1/stack:&quot;fcs-3&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet.VLAN&#x27;}}
Test Complete!
<br/></div></td></tr></tbody>
      <tbody class="passed results-table-row">
        <tr>
          <td class="col-result">Passed</td>
          <td class="col-name">traffic_tests/test_normal_traffic.py::test_normal_traffic</td>
          <td class="col-duration">42.31</td>
          <td class="col-links"></td></tr>
        <tr>
          <td class="extra" colspan="4">
            <div class="log"> -----------------------------Captured stdout setup------------------------------ <br/>ixiatcl:info: Tcl version: 8.6.6
otg(username=None, password=None, api_server=&#x27;10.39.47.41:8888&#x27;, chassis=&#x27;10.39.35.12&#x27;, ports=[&#x27;2/13&#x27;, &#x27;2/14&#x27;, &#x27;2/15&#x27;, &#x27;2/16&#x27;])
{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
<br/> ------------------------------Captured stdout call------------------------------ <br/>{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
[&#x27;1/2/13&#x27;, &#x27;1/2/14&#x27;, &#x27;1/2/15&#x27;, &#x27;1/2/16&#x27;]
Creating raw traffic
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI0-Traffic_0&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI1-Traffic_1&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:2/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:2/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:2/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI2-Traffic_2&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:3/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:3/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:3/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI3-Traffic_3&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:4/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:4/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:4/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI4-Traffic_4&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:5/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:5/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:5/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:5/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:5/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI5-Traffic_5&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:6/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:6/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:6/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:6/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:6/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI6-Traffic_6&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:7/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:7/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:7/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:7/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:7/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI7-Traffic_7&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:8/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:8/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:8/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:8/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:8/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:8/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:8/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:8/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI8-Traffic_8&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:9/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:9/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:9/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:9/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:9/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:9/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:9/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:9/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI9-Traffic_9&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:10/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:10/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:10/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:10/configElement:1/stack:&quot;fcs-2&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:10/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:10/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:10/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:10/highLevelStream:1/stack:&quot;fcs-2&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet&#x27;}}
Starting traffic for all items
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;0&#x27;}
Time taken: 4.260559558868408
Stopping traffic for all items
Traffic_Control PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;stopped&#x27;: &#x27;1&#x27;}
Time taken: 4.04538106918335
test complete!
<br/></div></td></tr></tbody>
      <tbody class="passed results-table-row">
        <tr>
          <td class="col-result">Passed</td>
          <td class="col-name">traffic_tests/test_traffic_modify.py::test_traffic_modify</td>
          <td class="col-duration">16.01</td>
          <td class="col-links"></td></tr>
        <tr>
          <td class="extra" colspan="4">
            <div class="log"> -----------------------------Captured stdout setup------------------------------ <br/>ixiatcl:info: Tcl version: 8.6.6
otg(username=None, password=None, api_server=&#x27;10.39.47.41:8888&#x27;, chassis=&#x27;10.39.35.12&#x27;, ports=[&#x27;2/13&#x27;, &#x27;2/14&#x27;, &#x27;2/15&#x27;, &#x27;2/16&#x27;])
{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
<br/> ------------------------------Captured stdout call------------------------------ <br/>{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
[&#x27;1/2/13&#x27;, &#x27;1/2/14&#x27;, &#x27;1/2/15&#x27;, &#x27;1/2/16&#x27;]
creating traffic ......
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI0-HLTAPI_TRAFFICITEM_540&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;udp-3&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;fcs-4&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;udp-3&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;fcs-4&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet.IPv4.UDP&#x27;}}
modifying ip ttl
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI0-HLTAPI_TRAFFICITEM_540&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;udp-3&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;fcs-4&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;udp-3&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;fcs-4&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet.IPv4.UDP&#x27;}, &#x27;last_stack&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;fcs-4&quot;&#x27;}
modifying ip addresses
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI0-HLTAPI_TRAFFICITEM_540&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;udp-3&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;fcs-4&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;udp-3&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;fcs-4&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet.IPv4.UDP&#x27;}, &#x27;last_stack&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;fcs-4&quot;&#x27;}
Test Complete !!!
<br/></div></td></tr></tbody>
      <tbody class="passed results-table-row">
        <tr>
          <td class="col-result">Passed</td>
          <td class="col-name">traffic_tests/test_traffic_sample.py::test_create_traffic_sample</td>
          <td class="col-duration">15.02</td>
          <td class="col-links"></td></tr>
        <tr>
          <td class="extra" colspan="4">
            <div class="log"> -----------------------------Captured stdout setup------------------------------ <br/>ixiatcl:info: Tcl version: 8.6.6
otg(username=None, password=None, api_server=&#x27;10.39.47.41:8888&#x27;, chassis=&#x27;10.39.35.12&#x27;, ports=[&#x27;2/13&#x27;, &#x27;2/14&#x27;, &#x27;2/15&#x27;, &#x27;2/16&#x27;])
{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
<br/> ------------------------------Captured stdout call------------------------------ <br/>{&#x27;port_handle&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;2/13&#x27;: &#x27;1/2/13&#x27;, &#x27;2/14&#x27;: &#x27;1/2/14&#x27;, &#x27;2/15&#x27;: &#x27;1/2/15&#x27;, &#x27;2/16&#x27;: &#x27;1/2/16&#x27;}}}}}, &#x27;connection&#x27;: {&#x27;tcl_port&#x27;: &#x27;8888&#x27;, &#x27;using_tcl_proxy&#x27;: &#x27;0&#x27;, &#x27;server_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;port&#x27;: &#x27;8888&#x27;, &#x27;chassis&#x27;: {&#x27;10&#x27;: {&#x27;39&#x27;: {&#x27;35&#x27;: {&#x27;12&#x27;: {&#x27;hostname&#x27;: &#x27;10.39.35.12&#x27;, &#x27;ip&#x27;: &#x27;10.39.35.12&#x27;, &#x27;chassis_protocols_version&#x27;: &#x27;Ignored&#x27;, &#x27;chassis_type&#x27;: &#x27;Optixia XM12&#x27;, &#x27;chassis_version&#x27;: &#x27;IxOS 9.10.0.247 EB&#x27;, &#x27;is_master_chassis&#x27;: &#x27;1&#x27;, &#x27;chain_type&#x27;: &#x27;daisy&#x27;, &#x27;chassis_chain&#x27;: {&#x27;sequence_id&#x27;: &#x27;1&#x27;}}}}}}, &#x27;client_version&#x27;: &#x27;9.10.2007.7&#x27;, &#x27;username&#x27;: &#x27;IxNetwork/1UAC-X0670812/admin06&#x27;, &#x27;hostname&#x27;: &#x27;1UAC-X0670812&#x27;, &#x27;license&#x27;: {&#x27;server&#x27;: &#x27;localhost&#x27;, &#x27;type&#x27;: &#x27;mixed_tier3&#x27;}}, &#x27;vport_list&#x27;: &#x27;1/2/13 1/2/14 1/2/15 1/2/16&#x27;, &#x27;vport_protocols_handle&#x27;: &#x27;::ixNet::OBJ-/vport:1/protocols ::ixNet::OBJ-/vport:2/protocols ::ixNet::OBJ-/vport:3/protocols ::ixNet::OBJ-/vport:4/protocols&#x27;, &#x27;guardrail_messages&#x27;: {&#x27;1&#x27;: &#x27;MESSAGE: Guardrails Monitor - IxNetwork was unable to establish a successful connection with IxMonitor service. Guard Rails resource monitoring is deactivated.&#x27;, &#x27;2&#x27;: &#x27;WARNING: IxNetwork main module errors - Ignore Version Registry Key is Enabled.&#x27;, &#x27;3&#x27;: &#x27;MESSAGE: StatViewer Guardrail Info - The statistics Guard Rail option is designed to protect you from adding too many statistics. It is recommended to keep this option enabled, in order to prevent inaccurate statistics while running large scale tests.&#x27;}, &#x27;status&#x27;: &#x27;1&#x27;}
[&#x27;1/2/13&#x27;, &#x27;1/2/14&#x27;, &#x27;1/2/15&#x27;, &#x27;1/2/16&#x27;]
creating traffic ......
traffic_created === {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI0-HLTAPI_TRAFFICITEM_540&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;fcs-3&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;fcs-3&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet.IPv4&#x27;}}
Traffic_Config PASSED:: Log: {&#x27;status&#x27;: &#x27;1&#x27;, &#x27;log&#x27;: &#x27;&#x27;, &#x27;stream_id&#x27;: &#x27;TI0-HLTAPI_TRAFFICITEM_540&#x27;, &#x27;traffic_item&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:1/configElement:1/stack:&quot;fcs-3&quot;&#x27;, &#x27;stream_ids&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;, &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1&#x27;: {&#x27;headers&#x27;: &#x27;::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;ethernet-1&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;ipv4-2&quot; ::ixNet::OBJ-/traffic/trafficItem:1/highLevelStream:1/stack:&quot;fcs-3&quot;&#x27;}, &#x27;endpoint_set_id&#x27;: &#x27;1&#x27;, &#x27;encapsulation_name&#x27;: &#x27;Ethernet.IPv4&#x27;}}
test complete!!!!
<br/></div></td></tr></tbody></table></body></html>
