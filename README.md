# Vender Code Management
## Making changes to third party code safely and without loosing mergability
So... you found this great library from Bob The Vendor, the language you use doesn't support inheritance well or for some other reason you need to add the code into your repository.

Or third party code that comes as source AND bugs! You can't wait for upstream to fix the bug that you discovered (because you are the only customer doing X). You decide to check in their source and then modify it.

BUT WAIT! What happens when Bob Upstream fixes the bugs? Or releases a new version where the bug may be fixed?  You don't want to lose your fixes in..  but you also do not want to miss out on new features.

Vendor Branch Management to the RESCUE!

General flow:

 * Branch for vendor
 * Add code to vendor branch
 * PROTECT BRANCH - you do not want anyone modifying files here without oversight.
 * Branch from vendor branch for your modifications...
 * Merge your branch into mainline and everything is good.
 
Bob release version 2
 * checkout vendor branch
 * commit version 2
 * create branch from Main 
 * merge new vendor code with your changes.
 * handle conflicts
 * PR bakc to main and good to go.
 
Yes, that seems like a lot of work.  However this is IMO very much worth the effort. I've used this technique for decades and it's very effective at allowing change without creating a mess.

It's doubly handy when upstream finally fixes your bug and you can simply drop your changes and use unmodified vendor code.