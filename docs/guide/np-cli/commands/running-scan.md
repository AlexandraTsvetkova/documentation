# 🏃 Running a Scan
```nexploit-cli scan:run [options]``` starts a new scan with the received configuration.
>[!NOTE|label:Note]
If the maximum number of scans that can be run simultaneously is exceeded, the scan is placed in the queue. The concurrent scans limitation can be set either for the entire organization or for this particular project in the project settings. The new scan will start as soon as you manually stop another running scan or when the current scan is completed.

This command enables you to specify one or more discovery strategies. For example, using the `--crawler` option and/or the generated HAR files, separately or concurrently. This means that you can handle client-side dynamic content, javascript and so on.

## Options

<table id="simple-table">
<tr>
<th width=27%><strong>Option</strong></th>
<th><strong>Description</strong></th>
</tr>
<tr>
<td><code>--token my-jwt-authentication-token</code></td>
<td>The unique identifier used to authenticate a user. The token (API key) can be issued in your organization’s dashboard.</td>
</tr>
<tr>
<td><code>--name=extraHeader</code>,<br><code>-n=extraHeader</code></td>
<td>The name of the scan.</td>
</tr>
<tr>
<td><code>--archive=archiveID</code>,<br><code>-a=archiveID</code></td>
<td>The Archive ID, which can be received via the&nbsp;archive:upload&nbsp;command.</td>
</tr>
<tr>
<td><code>--crawler=url</code>,<br><code>-c=url</code></td>
<td >Specifies a list of specific URLs that should be included during crawler discovery.</td>
</tr>
<tr>
<td><code>--repeater=uuid</code></td>
<td>Specifies a list of Repeater UUIDs that should be connected with the scan.</td>
</tr>
<tr>
<td><code>--smart</code></td>
<td>Enables you to use automatic smart decisions, such as parameter skipping, detection phases and so on to minimize scan time. When turned off, all tests are run on all the parameters, which increases the coverage at the expense of scan time.</td>
</tr>
<tr>
<td><code>--param=path/query/fragment<br>/header/body</code></td>
<td>Defines which part of the request to attack (see <a href="#/guide/np-web-ui/scanning/creating-new-scan?id=target-params-locations">here</a> for more details).<br><br> <strong><font color="#0ba9b8">Note:</font></strong> This argument can be passed multiple times in the same command.<br><br><strong>Default:</strong>&nbsp;<code>--parameter body query fragment</code>.</td>
</tr>
<tr>
<td><code>--module=dast/fuzzer</code></td>
<td>The DAST module tests for specific scenarios, such as OWASP top 10 and other common scenarios. The fuzzer module generates various new scenarios in order to test for unknown issues, providing automated AI-guided fuzz testing.<br><br><strong>Default:</strong> <code>--module dast</code></td>
</tr>
<tr>
<td><code>--host-filter=hostOrIp</code>,<br><code>-F=hostOrIp</code></td>
<td>The list of specific hosts to be included in the scan.</td>
</tr>
<tr>
<td><code>--header=extraHeader</code>,<br><code>-H=extraHeader</code></td>
<td>Extra headers to be passed with the archive file. It can also be used to remove a header by providing a name without content. For example, -H "Host:". <br><br><strong><font color="red">Warning:</font></strong> Headers set with this option override the archive headers and are set in all the requests.</td>
</tr>
<tr>
<td><code>--test=testName</code></td>
<td>Specifies a list of relevant tests to execute during a scan.<br>For example, <code>--test default_login_location dom_xss</code>.</td>
</tr>
<tr>
<td><code>--api=ApiDomain</code></td>
<td>Set the API endpoint domain, for VPC, use: <code>--api https://private-domain.nexploit.app</code> <br><br><strong>Default:</strong> <code>--api https://nexploit.app</code></td>
</tr>
<tr>
<td><code>--auth=authObjectID</code></td>
<td>Specifies the ID of the authentication object to be connect to the scan. Find more info about using an authentication object at <a href="#/guide/np-web-ui/scanning/managing-authentications/managing-your-authentications">Manging Your Authentications</a>.</td>
</tr>
</table>
