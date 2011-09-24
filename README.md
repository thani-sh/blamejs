#Git Blame parser in JavaScript

This module parses the output from a "git blame -p" (for porcelain, i.e. machine-digestible) operation.

#Usage

```javascript
var BlameJS = require("blamejs");
var blamejs = new BlameJS();

// Get the result of the git blame operation
var blameOut = "[output]";

blamejs.parseBlame(blameOut);

// Get the commit data
var commitData = blamejs.getCommitData();

// Get the line data array, each item containing a reference to
// commits that can be then referenced in commitData
var lineData = blamejs.getLineData();

var firstLine = commitData[lineData[0].hash];
// firstLine now has:
// - author
// - authorMail
// - authorTime
// - authorTz
// - committer
// - committerMail
// - committerTime
// - committerTz 
// - summary
// - previousHash
// - filename
