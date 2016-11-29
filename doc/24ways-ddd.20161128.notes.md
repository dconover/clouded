#
 
owner: dconover:20161128

## overview

## reference
  1. https://24ways.org/2010/documentation-driven-design-for-apis/

## quotes

```bash
Documentation-Driven Design for APIs

 Frances Berriman Frances Berriman

Documentation is like gift wrapping. It seems like superfluous fluff, but your family tends to be rather disappointed when their presents arrive in supermarket carrier bags, so you have to feign some sort of attempt at making your gift look enticing. Documentation doesn’t have to be all hard work and sellotaping yourself to a table – you can make it useful and relevant.

Documentation gets a pretty rough deal. It tends to get left until the end of a project, when some poor developer is assigned the ‘document project’ ticket and wades through each feature of Whizzy New
API 3.0 and needs to recall exactly what each method is meant to do. That’s assuming any time is left for documentation at all. The more common outcome resembles last minute homework scribbled on a post-it note, where just the bare bones of what’s available are put out for your users, and you hope that you’ll spot the inconsistencies and mistakes before they do.

Wouldn’t it be nicer for everyone if you could make documentation not only outstanding for your users, but also a valuable tool for your development team – so much so that you couldn’t imagine writing a line of code before you’d documented it?

Documentation needs to have three main features:

It should have total coverage and document all the features of your project. Private methods should be documented for your developers, and public features need to be available to your users.
It should be consistent – a user should know what to expect from your documentation, and terminology should be accurate to your language.
It should be current – and that means staying accurate as new versions of your code base are released.
But you can also get these bonuses:

Act as a suggested specification – a guide that will aid a developer in making something consistent and usable.
It can test your API quality.
It can enhance the communication skills within your development team.
So how do we get our documentation to be rich and full of features, instead of a little worn out like Boxing Day leftovers?

Write your documentation first

When I say first, I mean first. Not after you’ve started writing the code. Not even after you’ve started writing your unit tests. First. You may or may not have been provided with a decent specification, but the first job should be to turn your requirements for a feature into documentation.

It works best when it takes the form of in-code comments. It works even better when your in-code comments take a standard documentation format that you can later use to generate published documentation for your users. This has the benefit of immediately making your docs as version controlled as your code-base, and it saves having to rewrite, copy or otherwise harass your docs into something legible later on.

Almost all languages have a self-documentation format these days. My choice of format for JavaScript is JSDocToolkit, and the sort of things I look for are the ability to specify private and public methods, full options object statements (opts as Opts only is a no-no), and the ability to include good examples.

So, our example for today will be a new festive feature for a JavaScript API. We’ve been asked to specify a sled for Santa to get around the world to give out toys:

Santa needs to be able to travel around the world in one night to deliver toys to children, and he’ll need some reindeer to pull his sled.

As documentation, it would look like:

/**
@name Sled
@extends Vehicle
@constructor
@description Create a new sled to send Santa around the world to deliver toys to good kids.
	@param {Object} [opts] Options
	@param {number} [opts.capacity='50'] Set the capacity of the sled
	@param {string} [opts.pilot='santa'] The pilot of the sled.
@example
	// Create a sled and specify some reindeer.
	new Sled().reindeer(['Dasher', 'Dancer', 'Prancer', 'Vixen', 'Comet', 'Cupid']);
*/
By breaking it down as documentation, you can, for example, hand this over to another developer without the need to explain the feature in much depth, and they’ll develop something that has to match this piece of documentation. It specifies everything that is important to this feature – its default values and types, and where it inherits other features from.

We know that we need to specify some way of setting reindeer to pull the sled and also some toys to give, and so we can quickly specify extra methods for the sled:

/*
@name vehicle.Sled#reindeer
@function
@description Set the reindeer that will pull Santa's sled.
	@param {string[]} reindeer A list of the reindeer.
@example
	// specifying some reindeer
	Sled().reindeer(['Dasher', 'Dancer', 'Rudolph', 'Vixen']);
*/
/*
@name vehicle.Sled#toys
@function
@description Add a list of toys and recipients to the Sled.
	@param {Object[]} toys A list of toys and who will receive them.
@example
	// Adding toys to the sled
	Sled().toys([
		{name:'Brian', toy:'Fire Engine'},
		{name:'Drew', toy:'Roller-skates'},
		{name:'Anna', toy:'Play-doh'},
		...
		]);
*/
Job done! You’ve got a specification to share with your team and something useful for your users in the form of full examples, and you didn’t even have to open another text editor.

Use your documentation to share knowledge

Documentation isn’t just for users. It’s also used by internal developers to explain what they’ve written and how it works. This is especially valuable where the team is large or the code-base sprawling.

So, returning to our example, the next step would be to share with the rest of the team (or at least a selection of the team if yours is large) what the documentation looks like. This is useful for two main reasons:

They can see if they understand what the documentation says the feature will do. It’s best if they haven’t seen the requirement before. If your fellow developers can’t work out what ‘MagicMethodX’ is going to return from the docs, neither can your users.
They can check that the feature accomplishes everything that they expect to, and that it’s consistent with the rest of the functionality.
On previous projects, we’ve taken to referring to this stage of the development process as the ‘bun fight’. It’s a chance for everyone to have an honest say and throw a few pies without actually causing anyone to have to rewrite any code. If you can identify at this stage that a feature is over-complicated, lacking or just plain useless, you’ll all be much happier to throw out a few lines of documentation than you may have been to throw out a partial, or even complete, piece of functionality.

Documentation has your back

The final benefit to working in this way is that your documentation not only remains accurate, it’s always as accurate as your latest release. It can’t fall behind. You can increase the likelihood that your docs will remain up to date by unit testing your examples.

Returning to the previous example, we can add a QUnit unit test to the expected output with ease during the build process – we know exactly how the code will look and, with the @example tag, we can identify easily where to find the bits that need testing. If it’s tested it’ll definitely work as you expect it to when a user copy and pastes it. You’re ensuring quality from idea to implementation.

As an extra bauble, the best thing about a system like JSDocToolkit is that it’ll take your inline comments and turn them into beautiful sites, as good systems will allow for customised output templates. You’ll be producing full-featured sites for your projects and plugins with almost no extra effort, but all the benefits.
```
