---
id: SecurityTokenRegistry
title: SecurityTokenRegistry
---

<div class="contract-doc"><div class="contract"><h2 class="contract-header"><span class="contract-kind">contract</span> SecurityTokenRegistry</h2><p class="base-contracts"><span>is</span> <a href="interfaces_ISecurityTokenRegistry.html">ISecurityTokenRegistry</a><span>, </span><a href="helpers_Util.html">Util</a><span>, </span><a href="Pausable.html">Pausable</a><span>, </span><a href="RegistryUpdater.html">RegistryUpdater</a><span>, </span><a href="ReclaimTokens.html">ReclaimTokens</a></p><div class="source">Source: <a href="git+https://github.com/PolymathNetwork/polymath-core/blob/v1.3.3/contracts/SecurityTokenRegistry.sol" target="_blank">SecurityTokenRegistry.sol</a></div></div><div class="index"><h2>Index</h2><ul><li><a href="SecurityTokenRegistry.html#LogAddCustomSecurityToken">LogAddCustomSecurityToken</a></li><li><a href="SecurityTokenRegistry.html#LogChangePolyRegisterationFee">LogChangePolyRegisterationFee</a></li><li><a href="SecurityTokenRegistry.html#LogNewSecurityToken">LogNewSecurityToken</a></li><li><a href="SecurityTokenRegistry.html#addCustomSecurityToken">addCustomSecurityToken</a></li><li><a href="SecurityTokenRegistry.html#changePolyRegisterationFee">changePolyRegisterationFee</a></li><li><a href="SecurityTokenRegistry.html#">fallback</a></li><li><a href="SecurityTokenRegistry.html#generateSecurityToken">generateSecurityToken</a></li><li><a href="SecurityTokenRegistry.html#getSecurityTokenAddress">getSecurityTokenAddress</a></li><li><a href="SecurityTokenRegistry.html#getSecurityTokenData">getSecurityTokenData</a></li><li><a href="SecurityTokenRegistry.html#isSecurityToken">isSecurityToken</a></li><li><a href="SecurityTokenRegistry.html#pause">pause</a></li><li><a href="SecurityTokenRegistry.html#setProtocolVersion">setProtocolVersion</a></li><li><a href="SecurityTokenRegistry.html#unpause">unpause</a></li></ul></div><div class="reference"><h2>Reference</h2><div class="events"><h3>Events</h3><ul><li><div class="item event"><span id="LogAddCustomSecurityToken" class="anchor-marker"></span><h4 class="name">LogAddCustomSecurityToken</h4><div class="body"><code class="signature">event <strong>LogAddCustomSecurityToken</strong><span>(string _name, string _symbol, address _securityToken, uint256 _addedAt) </span></code><hr/><dl><dt><span class="label-parameters">Parameters:</span></dt><dd><div><code>_name</code> - string</div><div><code>_symbol</code> - string</div><div><code>_securityToken</code> - address</div><div><code>_addedAt</code> - uint256</div></dd></dl></div></div></li><li><div class="item event"><span id="LogChangePolyRegisterationFee" class="anchor-marker"></span><h4 class="name">LogChangePolyRegisterationFee</h4><div class="body"><code class="signature">event <strong>LogChangePolyRegisterationFee</strong><span>(uint256 _oldFee, uint256 _newFee) </span></code><hr/><dl><dt><span class="label-parameters">Parameters:</span></dt><dd><div><code>_oldFee</code> - uint256</div><div><code>_newFee</code> - uint256</div></dd></dl></div></div></li><li><div class="item event"><span id="LogNewSecurityToken" class="anchor-marker"></span><h4 class="name">LogNewSecurityToken</h4><div class="body"><code class="signature">event <strong>LogNewSecurityToken</strong><span>(string _ticker, address _securityTokenAddress, address _owner) </span></code><hr/><dl><dt><span class="label-parameters">Parameters:</span></dt><dd><div><code>_ticker</code> - string</div><div><code>_securityTokenAddress</code> - address</div><div><code>_owner</code> - address</div></dd></dl></div></div></li></ul></div><div class="functions"><h3>Functions</h3><ul><li><div class="item function"><span id="addCustomSecurityToken" class="anchor-marker"></span><h4 class="name">addCustomSecurityToken</h4><div class="body"><code class="signature">function <strong>addCustomSecurityToken</strong><span>(string _name, string _symbol, address _owner, address _securityToken, string _tokenDetails, bytes32 _swarmHash) </span><span>public </span></code><hr/><div class="description"><p>Add a new custom (Token should follow the ISecurityToken interface) Security Token and saves it to the registry.</p></div><dl><dt><span class="label-modifiers">Modifiers:</span></dt><dd><a href="es_openzeppelin-solidity_contracts_ownership_Ownable.html#onlyOwner">onlyOwner </a><a href="Pausable.html#whenNotPaused">whenNotPaused </a></dd><dt><span class="label-parameters">Parameters:</span></dt><dd><div><code>_name</code> - Name of the token</div><div><code>_symbol</code> - Ticker symbol of the security token</div><div><code>_owner</code> - Owner of the token</div><div><code>_securityToken</code> - Address of the securityToken</div><div><code>_tokenDetails</code> - off-chain details of the token</div><div><code>_swarmHash</code> - off-chain details about the issuer company</div></dd></dl></div></div></li><li><div class="item function"><span id="changePolyRegisterationFee" class="anchor-marker"></span><h4 class="name">changePolyRegisterationFee</h4><div class="body"><code class="signature">function <strong>changePolyRegisterationFee</strong><span>(uint256 _registrationFee) </span><span>public </span></code><hr/><div class="description"><p>Set the ticker registration fee in POLY tokens.</p></div><dl><dt><span class="label-modifiers">Modifiers:</span></dt><dd><a href="es_openzeppelin-solidity_contracts_ownership_Ownable.html#onlyOwner">onlyOwner </a></dd><dt><span class="label-parameters">Parameters:</span></dt><dd><div><code>_registrationFee</code> - registration fee in POLY tokens (base 18 decimals)</div></dd></dl></div></div></li><li><div class="item function"><span id="fallback" class="anchor-marker"></span><h4 class="name">fallback</h4><div class="body"><code class="signature">function <strong></strong><span>(address _polymathRegistry, address _stVersionProxy, uint256 _registrationFee) </span><span>public </span></code><hr/><dl><dt><span class="label-modifiers">Modifiers:</span></dt><dd></dd><dt><span class="label-parameters">Parameters:</span></dt><dd><div><code>_polymathRegistry</code> - address</div><div><code>_stVersionProxy</code> - address</div><div><code>_registrationFee</code> - uint256</div></dd></dl></div></div></li><li><div class="item function"><span id="generateSecurityToken" class="anchor-marker"></span><h4 class="name">generateSecurityToken</h4><div class="body"><code class="signature">function <strong>generateSecurityToken</strong><span>(string _name, string _symbol, string _tokenDetails, bool _divisible) </span><span>public </span></code><hr/><div class="description"><p>Creates a new Security Token and saves it to the registry.</p></div><dl><dt><span class="label-modifiers">Modifiers:</span></dt><dd><a href="Pausable.html#whenNotPaused">whenNotPaused </a></dd><dt><span class="label-parameters">Parameters:</span></dt><dd><div><code>_name</code> - Name of the token</div><div><code>_symbol</code> - Ticker symbol of the security token</div><div><code>_tokenDetails</code> - off-chain details of the token</div><div><code>_divisible</code> - Set to true if token is divisible</div></dd></dl></div></div></li><li><div class="item function"><span id="getSecurityTokenAddress" class="anchor-marker"></span><h4 class="name">getSecurityTokenAddress</h4><div class="body"><code class="signature">function <strong>getSecurityTokenAddress</strong><span>(string _symbol) </span><span>public </span><span>view </span><span>returns  (address) </span></code><hr/><div class="description"><p>Get security token address by ticker name.</p></div><dl><dt><span class="label-parameters">Parameters:</span></dt><dd><div><code>_symbol</code> - Symbol of the Scurity token</div></dd><dt><span class="label-return">Returns:</span></dt><dd>address</dd></dl></div></div></li><li><div class="item function"><span id="getSecurityTokenData" class="anchor-marker"></span><h4 class="name">getSecurityTokenData</h4><div class="body"><code class="signature">function <strong>getSecurityTokenData</strong><span>(address _securityToken) </span><span>public </span><span>view </span><span>returns  (string, address, string) </span></code><hr/><div class="description"><p>Get security token data by its address.</p></div><dl><dt><span class="label-parameters">Parameters:</span></dt><dd><div><code>_securityToken</code> - Address of the Scurity token</div></dd><dt><span class="label-return">Returns:</span></dt><dd>string</dd></dl></div></div></li><li><div class="item function"><span id="isSecurityToken" class="anchor-marker"></span><h4 class="name">isSecurityToken</h4><div class="body"><code class="signature">function <strong>isSecurityToken</strong><span>(address _securityToken) </span><span>public </span><span>view </span><span>returns  (bool) </span></code><hr/><div class="description"><p>Check that Security Token is registered.</p></div><dl><dt><span class="label-parameters">Parameters:</span></dt><dd><div><code>_securityToken</code> - Address of the Scurity token</div></dd><dt><span class="label-return">Returns:</span></dt><dd>bool</dd></dl></div></div></li><li><div class="item function"><span id="pause" class="anchor-marker"></span><h4 class="name">pause</h4><div class="body"><code class="signature">function <strong>pause</strong><span>() </span><span>public </span></code><hr/><div class="description"><p>Unpause registration function.</p></div><dl><dt><span class="label-modifiers">Modifiers:</span></dt><dd><a href="es_openzeppelin-solidity_contracts_ownership_Ownable.html#onlyOwner">onlyOwner </a></dd></dl></div></div></li><li><div class="item function"><span id="setProtocolVersion" class="anchor-marker"></span><h4 class="name">setProtocolVersion</h4><div class="body"><code class="signature">function <strong>setProtocolVersion</strong><span>(address _stVersionProxyAddress, bytes32 _version) </span><span>public </span></code><hr/><div class="description"><p>Changing versions does not affect existing tokens.</p></div><dl><dt><span class="label-modifiers">Modifiers:</span></dt><dd><a href="es_openzeppelin-solidity_contracts_ownership_Ownable.html#onlyOwner">onlyOwner </a></dd><dt><span class="label-parameters">Parameters:</span></dt><dd><div><code>_stVersionProxyAddress</code> - address</div><div><code>_version</code> - bytes32</div></dd></dl></div></div></li><li><div class="item function"><span id="unpause" class="anchor-marker"></span><h4 class="name">unpause</h4><div class="body"><code class="signature">function <strong>unpause</strong><span>() </span><span>public </span></code><hr/><div class="description"><p>Pause registration function.</p></div><dl><dt><span class="label-modifiers">Modifiers:</span></dt><dd><a href="es_openzeppelin-solidity_contracts_ownership_Ownable.html#onlyOwner">onlyOwner </a></dd></dl></div></div></li></ul></div></div></div>