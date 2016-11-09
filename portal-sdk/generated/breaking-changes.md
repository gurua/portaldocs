# Breaking Changes from 7/4/2016 
* Additional Q&A about breaking changes can be found [here](./breaking-changes.md) 
* To ask a question about breaking changes [use this](https://aka.ms/ask/ibiza-breaking-change)  


## 5.0.302.523
<table><tr><td><a href='http://vstfrd:8080/Azure/RD/_workitems#_a=edit&id=7488094'>7488094</a></td><td><a href='http://vstfrd:8080/Azure/RD/_workitems#_a=edit&id=7488094'>[ErrorTracker] content.valid writing to a read only observable</a><p>Previously the valid observable was not typed correctly so you would not get a compiler error when trying to write to it (instead it would show up at runtime as an MDS error). Now we're typing valid as read only so the compiler will flag issues in extension code. This does not change behavior at all since previously any writes to the valid() observable on controls were discarded and did nothing.</p></td></tr></table>

## 5.0.302.440
<table><tr><td><a href='http://vstfrd:8080/Azure/RD/_workitems#_a=edit&id=6725007'>6725007</a></td><td><a href='http://vstfrd:8080/Azure/RD/_workitems#_a=edit&id=6725007'>Launch notice blade when resource type does not support move operation</a><p>No description available for this breaking change.</p></td></tr></table>

## 5.0.302.431
<table><tr><td><a href='http://vstfrd:8080/Azure/RD/_workitems#_a=edit&id=6655921'>6655921</a></td><td><a href='http://vstfrd:8080/Azure/RD/_workitems#_a=edit&id=6655921'>ExtensionDefinition is now a required class</a><p></div><div><br></div><div>Extensions are expected to define a class that derives from Microsoft.Portal.Framework.ExtensionDefinition.</div><div>And export it with the following MEF attribute:</div><div><br>[Export(typeof(ExtensionDefinition))]</div><div>internal class MyExtensionDefinition : ExtensionDefinition&nbsp;&nbsp;&nbsp; </div><div><br></div><div>This has always been required and extensions who do not define this correctly tend to have unexpected behavior.</div><div>This change now enforces this and the extension will fail at app startup if such a class is not found.</div><div>This is to avoid the unexpected behavior at runtime.</div><div><br></div><div></p></td></tr><tr><td><a href='http://vstfrd:8080/Azure/RD/_workitems#_a=edit&id=6632356'>6632356</a></td><td><a href='http://vstfrd:8080/Azure/RD/_workitems#_a=edit&id=6632356'>Remove old hubs related code</a><p></div><div>Removes support for specifying hubs in PDL since hubs have been deprecated.</div><div></p></td></tr><tr><td><a href='http://vstfrd:8080/Azure/RD/_workitems#_a=edit&id=5637012'>5637012</a></td><td><a href='http://vstfrd:8080/Azure/RD/_workitems#_a=edit&id=5637012'>Resource move type validation</a><p></div><div>This change removes the supportsResourceMove option for the&nbsp;ResourceSummary view-model. Resources will be opted in automatically when the RP indicates the resource type supports moving resources between resource groups and/or subscriptions. Simply remove the option to resolve the build break. Contact ibizafxpm@microsoft.com if you need to opt out of resource move when your RP supports it.</div><div></p></td></tr></table>