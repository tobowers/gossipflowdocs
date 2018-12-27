<h1 id="gossip3">Gossip3</h1>
<h2 id="sync">Sync</h2>
<h3 id="full-flow">Full Flow</h3>
<div class="mermaid"><svg xmlns="http://www.w3.org/2000/svg" id="mermaid-svg-Dj28z5BkntQhwFQ1" height="100%" width="100%" style="max-width:550px;" viewBox="-150 -10 550 500"><g></g><g><line id="actor623" x1="75" y1="5" x2="75" y2="489" class="actor-line" stroke-width="0.5px" stroke="#999"></line><rect x="0" y="0" fill="#eaeaea" stroke="#666" width="150" height="65" rx="3" ry="3" class="actor"></rect><text x="75" y="32.5" dominant-baseline="central" alignment-baseline="central" class="actor" style="text-anchor: middle;"><tspan x="75" dy="0">SignerA</tspan></text></g><g><line id="actor624" x1="275" y1="5" x2="275" y2="489" class="actor-line" stroke-width="0.5px" stroke="#999"></line><rect x="200" y="0" fill="#eaeaea" stroke="#666" width="150" height="65" rx="3" ry="3" class="actor"></rect><text x="275" y="32.5" dominant-baseline="central" alignment-baseline="central" class="actor" style="text-anchor: middle;"><tspan x="275" dy="0">SignerB</tspan></text></g><defs><marker id="arrowhead" refX="5" refY="2" markerWidth="6" markerHeight="4" orient="auto"><path d="M 0,0 V 4 L6,2 Z"></path></marker></defs><defs><marker id="crosshead" markerWidth="15" markerHeight="8" orient="auto" refX="16" refY="4"><path fill="black" stroke="#000000" stroke-width="1px" d="M 9,2 V 6 L16,4 Z" style="stroke-dasharray: 0, 0;"></path><path fill="none" stroke="#000000" stroke-width="1px" d="M 0,1 L 6,7 M 6,1 L 0,7" style="stroke-dasharray: 0, 0;"></path></marker></defs><g><text x="175" y="93" class="messageText" style="text-anchor: middle;">GetSyncer</text><line x1="75" y1="100" x2="275" y2="100" class="messageLine0" stroke-width="2" stroke="black" marker-end="url(#arrowhead)" style="fill: none;"></line></g><g></g><g><text x="172.5" y="128" class="messageText" style="text-anchor: middle;">Address of Syncer</text><line x1="270" y1="135" x2="75" y2="135" class="messageLine0" stroke-width="2" stroke="black" marker-end="url(#arrowhead)" style="fill: none;"></line></g><g><text x="172.5" y="163" class="messageText" style="text-anchor: middle;">Difference Strata</text><line x1="75" y1="170" x2="270" y2="170" class="messageLine0" stroke-width="2" stroke="black" marker-end="url(#arrowhead)" style="fill: none;"></line></g><g><text x="172.5" y="198" class="messageText" style="text-anchor: middle;">Sized IBF</text><line x1="270" y1="205" x2="75" y2="205" class="messageLine0" stroke-width="2" stroke="black" marker-end="url(#arrowhead)" style="fill: none;"></line></g><g><rect x="-100" y="215" fill="#EDF2AE" stroke="#666" width="150" height="37" rx="0" ry="0" class="note"></rect><text x="-104" y="239" fill="black" class="noteText"><tspan x="-84" fill="black">Decodes IBF</tspan></text></g><g><text x="172.5" y="280" class="messageText" style="text-anchor: middle;">RequestKeys</text><line x1="75" y1="287" x2="270" y2="287" class="messageLine0" stroke-width="2" stroke="black" marker-end="url(#arrowhead)" style="fill: none;"></line></g><g><rect x="50" y="297" fill="#EDF2AE" stroke="#666" width="250" height="37" rx="0" ry="0" class="note"></rect><text x="46" y="321" fill="black" class="noteText"><tspan x="66" fill="black">The below happens in parallel</tspan></text></g><g><text x="172.5" y="362" class="messageText" style="text-anchor: middle;">Send wanted keys</text><line x1="270" y1="369" x2="75" y2="369" class="messageLine0" stroke-width="2" stroke="black" marker-end="url(#arrowhead)" style="fill: none;"></line></g><g><text x="172.5" y="397" class="messageText" style="text-anchor: middle;">Send wanted keys</text><line x1="75" y1="404" x2="270" y2="404" class="messageLine0" stroke-width="2" stroke="black" marker-end="url(#arrowhead)" style="fill: none;"></line></g><g><rect x="0" y="424" fill="#eaeaea" stroke="#666" width="150" height="65" rx="3" ry="3" class="actor"></rect><text x="75" y="456.5" dominant-baseline="central" alignment-baseline="central" class="actor" style="text-anchor: middle;"><tspan x="75" dy="0">SignerA</tspan></text></g><g><rect x="200" y="424" fill="#eaeaea" stroke="#666" width="150" height="65" rx="3" ry="3" class="actor"></rect><text x="275" y="456.5" dominant-baseline="central" alignment-baseline="central" class="actor" style="text-anchor: middle;"><tspan x="275" dy="0">SignerB</tspan></text></g></svg></div>
<h3 id="when-too-busy">When too busy</h3>
<div class="mermaid"><svg xmlns="http://www.w3.org/2000/svg" id="mermaid-svg-s351qOYiSwtw7ZgH" height="100%" width="100%" style="max-width:450px;" viewBox="-50 -10 450 231"><g></g><g><line id="actor625" x1="75" y1="5" x2="75" y2="220" class="actor-line" stroke-width="0.5px" stroke="#999"></line><rect x="0" y="0" fill="#eaeaea" stroke="#666" width="150" height="65" rx="3" ry="3" class="actor"></rect><text x="75" y="32.5" dominant-baseline="central" alignment-baseline="central" class="actor" style="text-anchor: middle;"><tspan x="75" dy="0">SignerA</tspan></text></g><g><line id="actor626" x1="275" y1="5" x2="275" y2="220" class="actor-line" stroke-width="0.5px" stroke="#999"></line><rect x="200" y="0" fill="#eaeaea" stroke="#666" width="150" height="65" rx="3" ry="3" class="actor"></rect><text x="275" y="32.5" dominant-baseline="central" alignment-baseline="central" class="actor" style="text-anchor: middle;"><tspan x="275" dy="0">BusySigner</tspan></text></g><defs><marker id="arrowhead" refX="5" refY="2" markerWidth="6" markerHeight="4" orient="auto"><path d="M 0,0 V 4 L6,2 Z"></path></marker></defs><defs><marker id="crosshead" markerWidth="15" markerHeight="8" orient="auto" refX="16" refY="4"><path fill="black" stroke="#000000" stroke-width="1px" d="M 9,2 V 6 L16,4 Z" style="stroke-dasharray: 0, 0;"></path><path fill="none" stroke="#000000" stroke-width="1px" d="M 0,1 L 6,7 M 6,1 L 0,7" style="stroke-dasharray: 0, 0;"></path></marker></defs><g><text x="175" y="93" class="messageText" style="text-anchor: middle;">GetSyncer</text><line x1="75" y1="100" x2="275" y2="100" class="messageLine0" stroke-width="2" stroke="black" marker-end="url(#arrowhead)" style="fill: none;"></line></g><g><rect x="270" y="102" fill="#f4f4f4" stroke="#666" width="10" height="33" rx="0" ry="0"></rect></g><g><text x="172.5" y="128" class="messageText" style="text-anchor: middle;">Too busy</text><line x1="270" y1="135" x2="75" y2="135" class="messageLine1" stroke-width="2" stroke="black" marker-end="url(#crosshead)" style="stroke-dasharray: 3, 3; fill: none;"></line></g><g><rect x="0" y="155" fill="#eaeaea" stroke="#666" width="150" height="65" rx="3" ry="3" class="actor"></rect><text x="75" y="187.5" dominant-baseline="central" alignment-baseline="central" class="actor" style="text-anchor: middle;"><tspan x="75" dy="0">SignerA</tspan></text></g><g><rect x="200" y="155" fill="#eaeaea" stroke="#666" width="150" height="65" rx="3" ry="3" class="actor"></rect><text x="275" y="187.5" dominant-baseline="central" alignment-baseline="central" class="actor" style="text-anchor: middle;"><tspan x="275" dy="0">BusySigner</tspan></text></g></svg></div>
<hr>
<h3 id="new-transaction">New Transaction</h3>
<div class="mermaid"><svg xmlns="http://www.w3.org/2000/svg" id="mermaid-svg-nVzE8kUiQ2uwTy8P" width="100%" style="max-width: 571.2578125px;" viewBox="0 0 571.2578125 452"><g transform="translate(-12, -12)"><g class="output"><g class="clusters"><g class="cluster" id="subGraph0" transform="translate(207.48828125,190)" style="opacity: 1;"><rect width="374.9765625" height="340" x="-187.48828125" y="-170"></rect><g class="label"><g transform="translate(0,0)"><foreignObject width="0" height="0"><div xmlns="http://www.w3.org/1999/xhtml" style="display: inline-block; white-space: nowrap;"></div></foreignObject></g></g><text x="0" y="-156" fill="black" stroke="none" id="mermaid-svg-nVzE8kUiQ2uwTy8PText" style="text-anchor: middle;">Transaction Verification</text></g></g><g class="edgePaths"><g class="edgePath" style="opacity: 1;"><path class="path" d="M224.796875,91L224.796875,129L224.796875,167" marker-end="url(#arrowhead7518)" style="fill:none"></path><defs><marker id="arrowhead7518" viewBox="0 0 10 10" refX="9" refY="5" markerUnits="strokeWidth" markerWidth="8" markerHeight="6" orient="auto"><path d="M 0 0 L 10 5 L 0 10 z" class="arrowheadPath" style="stroke-width: 1; stroke-dasharray: 1, 0;"></path></marker></defs></g><g class="edgePath" style="opacity: 1;"><path class="path" d="M191.3125,203.72023825142347L75.92578125,251L98.30577612704919,289" marker-end="url(#arrowhead7519)" style="fill:none"></path><defs><marker id="arrowhead7519" viewBox="0 0 10 10" refX="9" refY="5" markerUnits="strokeWidth" markerWidth="8" markerHeight="6" orient="auto"><path d="M 0 0 L 10 5 L 0 10 z" class="arrowheadPath" style="stroke-width: 1; stroke-dasharray: 1, 0;"></path></marker></defs></g><g class="edgePath" style="opacity: 1;"><path class="path" d="M240.8627049180328,213L267.40625,251L267.40625,289" marker-end="url(#arrowhead7520)" style="fill:none"></path><defs><marker id="arrowhead7520" viewBox="0 0 10 10" refX="9" refY="5" markerUnits="strokeWidth" markerWidth="8" markerHeight="6" orient="auto"><path d="M 0 0 L 10 5 L 0 10 z" class="arrowheadPath" style="stroke-width: 1; stroke-dasharray: 1, 0;"></path></marker></defs></g><g class="edgePath" style="opacity: 1;"><path class="path" d="M125.1116162909836,289L147.01953125,251L195.4709912909836,213" marker-end="url(#arrowhead7521)" style="fill:none"></path><defs><marker id="arrowhead7521" viewBox="0 0 10 10" refX="9" refY="5" markerUnits="strokeWidth" markerWidth="8" markerHeight="6" orient="auto"><path d="M 0 0 L 10 5 L 0 10 z" class="arrowheadPath" style="stroke-width: 1; stroke-dasharray: 1, 0;"></path></marker></defs></g><g class="edgePath" style="opacity: 1;"><path class="path" d="M258.28125,206.1966299095527L350.90625,251L445.4147028688525,289" marker-end="url(#arrowhead7522)" style="fill:none"></path><defs><marker id="arrowhead7522" viewBox="0 0 10 10" refX="9" refY="5" markerUnits="strokeWidth" markerWidth="8" markerHeight="6" orient="auto"><path d="M 0 0 L 10 5 L 0 10 z" class="arrowheadPath" style="stroke-width: 1; stroke-dasharray: 1, 0;"></path></marker></defs></g><g class="edgePath" style="opacity: 1;"><path class="path" d="M502.6171875,335L502.6171875,360L502.6171875,385L502.6171875,410" marker-end="url(#arrowhead7523)" style="fill:none"></path><defs><marker id="arrowhead7523" viewBox="0 0 10 10" refX="9" refY="5" markerUnits="strokeWidth" markerWidth="8" markerHeight="6" orient="auto"><path d="M 0 0 L 10 5 L 0 10 z" class="arrowheadPath" style="stroke-width: 1; stroke-dasharray: 1, 0;"></path></marker></defs></g></g><g class="edgeLabels"><g class="edgeLabel" transform="translate(224.796875,129)" style="opacity: 1;"><g transform="translate(-58.8203125,-13)" class="label"><foreignObject width="117.640625" height="26"><div xmlns="http://www.w3.org/1999/xhtml" style="display: inline-block; white-space: nowrap;"><span class="edgeLabel">New Transaction</span></div></foreignObject></g></g><g class="edgeLabel" transform="" style="opacity: 1;"><g transform="translate(0,0)" class="label"><foreignObject width="0" height="0"><div xmlns="http://www.w3.org/1999/xhtml" style="display: inline-block; white-space: nowrap;"><span class="edgeLabel"></span></div></foreignObject></g></g><g class="edgeLabel" transform="translate(267.40625,251)" style="opacity: 1;"><g transform="translate(-39.4296875,-13)" class="label"><foreignObject width="78.859375" height="26"><div xmlns="http://www.w3.org/1999/xhtml" style="display: inline-block; white-space: nowrap;"><span class="edgeLabel">If Not Valid</span></div></foreignObject></g></g><g class="edgeLabel" transform="translate(147.01953125,251)" style="opacity: 1;"><g transform="translate(-25.7890625,-13)" class="label"><foreignObject width="51.578125" height="26"><div xmlns="http://www.w3.org/1999/xhtml" style="display: inline-block; white-space: nowrap;"><span class="edgeLabel">IsValid?</span></div></foreignObject></g></g><g class="edgeLabel" transform="translate(350.90625,251)" style="opacity: 1;"><g transform="translate(-24.0703125,-13)" class="label"><foreignObject width="48.140625" height="26"><div xmlns="http://www.w3.org/1999/xhtml" style="display: inline-block; white-space: nowrap;"><span class="edgeLabel">If Valid</span></div></foreignObject></g></g><g class="edgeLabel" transform="" style="opacity: 1;"><g transform="translate(0,0)" class="label"><foreignObject width="0" height="0"><div xmlns="http://www.w3.org/1999/xhtml" style="display: inline-block; white-space: nowrap;"><span class="edgeLabel"></span></div></foreignObject></g></g></g><g class="nodes"><g class="node" id="MemPool" transform="translate(224.796875,68)" style="opacity: 1;"><rect rx="0" ry="0" x="-43.5859375" y="-23" width="87.171875" height="46"></rect><g class="label" transform="translate(0,0)"><g transform="translate(-33.5859375,-13)"><foreignObject width="67.171875" height="26"><div xmlns="http://www.w3.org/1999/xhtml" style="display: inline-block; white-space: nowrap;">MemPool</div></foreignObject></g></g></g><g class="node" id="Tupelo" transform="translate(224.796875,190)" style="opacity: 1;"><rect rx="0" ry="0" x="-33.484375" y="-23" width="66.96875" height="46"></rect><g class="label" transform="translate(0,0)"><g transform="translate(-23.484375,-13)"><foreignObject width="46.96875" height="26"><div xmlns="http://www.w3.org/1999/xhtml" style="display: inline-block; white-space: nowrap;">Tupelo</div></foreignObject></g></g></g><g class="node" id="ValidatorPool" transform="translate(111.8515625,312)" style="opacity: 1;"><rect rx="0" ry="0" x="-56.8515625" y="-23" width="113.703125" height="46"></rect><g class="label" transform="translate(0,0)"><g transform="translate(-46.8515625,-13)"><foreignObject width="93.703125" height="26"><div xmlns="http://www.w3.org/1999/xhtml" style="display: inline-block; white-space: nowrap;">ValidatorPool</div></foreignObject></g></g></g><g class="node" id="Delete" transform="translate(267.40625,312)" style="opacity: 1;"><rect rx="0" ry="0" x="-48.703125" y="-23" width="97.40625" height="46"></rect><g class="label" transform="translate(0,0)"><g transform="translate(-38.703125,-13)"><foreignObject width="77.40625" height="26"><div xmlns="http://www.w3.org/1999/xhtml" style="display: inline-block; white-space: nowrap;">Delete Key</div></foreignObject></g></g></g><g class="node" id="ConflictSetRouter" transform="translate(502.6171875,312)" style="opacity: 1;"><rect rx="0" ry="0" x="-72.640625" y="-23" width="145.28125" height="46"></rect><g class="label" transform="translate(0,0)"><g transform="translate(-62.640625,-13)"><foreignObject width="125.28125" height="26"><div xmlns="http://www.w3.org/1999/xhtml" style="display: inline-block; white-space: nowrap;">ConflictSetRouter</div></foreignObject></g></g></g><g class="node" id="ConflictSet" transform="translate(502.6171875,433)" style="opacity: 1;"><rect rx="0" ry="0" x="-48.90625" y="-23" width="97.8125" height="46"></rect><g class="label" transform="translate(0,0)"><g transform="translate(-38.90625,-13)"><foreignObject width="77.8125" height="26"><div xmlns="http://www.w3.org/1999/xhtml" style="display: inline-block; white-space: nowrap;">ConflictSet</div></foreignObject></g></g></g></g></g></g></svg></div>
