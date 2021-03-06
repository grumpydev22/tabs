# tabs

The tab component that I have created can be used multiple times on a page (assuming unique Id's are used for the tab panels) and can be styled as required. I have added some basic styling with the "tabs-style-a" class on the .tabs div but if this class is removed then there is no styling other than that which is needed for the functionality to show and hide panels, this allow the functionality to be used without being tied into a particular style.


The show/hide of the panels is done via css, the JS is just adding and removing the classes needed to do this, again this is for separation of styling and functionality, also jQuery is expensive when it comes to animation so if I were to animate the tabs I'd rather do this in css which will be a little more performant.

I haven't added any animation in my example as I don't think it's needed for a tab system, the user will most likely not see the animation of the panel growing so an animation would have a performance cost with little benefit (would have to calculate heights on each hashchange, not very efficient. Alternatively could do on page load and window resize but still a performance cost for little benefit and only becomes more costly with more tabs). If a client required an animation I could of course add this functionality in.


My smallscreen solution was to have the tabs turn into stacked tabs like an accordion, I feel this is intuitive to use and makes sense semantically as I was able to use a section header as the tab 'handle' and simple hide the desktop tab list at smallscreen.

My other considerations were to still have the tab list but style the tabs to go full width and stack but in a cms there could be any number of tabs and on a mobile the content could end up being far below the tab handles which may be a little disjointed for the user.

Another option I briefly considered was to turn the tab handles into a pseudo select box that would perhaps expand on click and allow the user to then choose, the box would then contract and the tab panel would have changed. Although I think this solution will work just fine it felt over-engineered for what it is.

You'll notice my JS is reasonably verbose (not talking about the comments), multiple variables created when I could concatenate, etc. This is a conscious decision, I like JS to be readable and easy to debug, if there's a problem on a server I don't have direct access to (e.g. production) then fixing a bug the client has found will suddenly become infinitely more critical then a kb or two saving I made whilst minifying my own code as I went along. Obviously this is debatable and is just my opinion, each company works differently.