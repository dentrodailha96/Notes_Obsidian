- Docker has an internal copy-on-write mechanism to reduce the amount of disk space required.

> Copy-on-write is a standard optimization strategy used in computing. When you create a new object (of any type) from a template, rather than copying the entire set of data required, you only copy data over when it’s changed. Depending on the use case, this can save considerable resources.

![[Pasted image 20251025173555.png]]