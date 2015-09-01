# Code-Along: Parrot

## Objectives

1. Create variables.
2. Call methods to manipulate strings.
3. Concatenate strings with methods on `NSString` and `NSMutableString`.
3. Print to the console with `NSLog()` supplied with interpolated strings.

## Instructions

This code-along lab will walk you through creating, manipulating, and concatenating (combining) strings while printing them with `NSLog()`.

Open the `objc-parrot.xcodeproj` file and navigate to the `FISAppDelegate.m` implementation file. You'll enter all of your code in the `application:didFinishLaunchingWithOptions:` method body before the `return YES` line.

**Top-tip:** *If you wish to play around with Objective-C code snippets, this location in a blank program (or one of these early labs that we're supplying to you) is the best option for a "playground". Objective-C is not accurately supported by any REPL or by playgrounds like many other programming languages including Swift. It takes a full Xcode project to run code snippets.*

#### Code-Along I: "Squawk!"

1. Print the string `@"Squawk!"` to the console by placing it directly inside an `NSLog()`:
  * `NSLog(@"Squawk!");`  
  * Run the program with `⌘``R`, this will print `Squawk!`.
2. Create an `NSString` variable called `squawk` and set it equal to a string literal `@"squawk"` in all lowercase, then submit it to an `NSLog()` as format argument:
  * `NSString *squawk = @"squawk";`
  * `NSLog(@"%@", squawk);`
  * Run the program with `⌘``R`, this will print `squawk`.
3. Now, set the `squawk` string variable equal to a call of the `uppercaseString` method on itself:
  * `squawk = [squawk capitalizedString];`
4. Then add an `!` to `squawk` by setting it equal to a call of `stringByAppendingString` on itself:
  * `squawk = [squawk stringByAppendingString:@"!"];`
5. Now, print `squawk` to the console using `NSLog()`:
  * `NSLog(@"%@", squawk);`
  * Run the program with `⌘``R`, this will print `Squawk!`.

At the end of this code-along your console should print out:

```
Squawk!
squawk
Squawk!
```

#### Code-Along II: "Dead men tell no tales!"

1. Create three `NSString` variables; `deadMen`, `tell`, and `noTales`; and set them equal to, respectively, `@"Dead men"`, `@"tell"`, and `@"no tales"`:
  * `NSString *deadMen = @"Dead men";`
  * `NSString *tell = @"tell";`
  * `NSString *noTales = @"no tales";`
2. Use the formatting ability of `NSLog()` to print these three string concatenated into a regular sentence, with a space between each format specifier and an exclamation point (`!`) at the end:
  * `NSLog(@"%@ %@ %@!", deadMen, tell, noTales);`
  * Run the program with `⌘``R`, this will print `Dead men tell no tales!`.
3. Create a new `NSMutableString` variable called `pirateParrot` and set it equal to an `+alloc` `-init` of a new `NSMutableString`:
  * `NSMutableString *pirateParrot = [[NSMutableString alloc] init];`
4. Now, append `deadMen` to `pirateParrot` by calling the `appendString:` method on `pirateParrot` with `deadMen` supplied as the argument, and then print `pirateParrot` to the console using an `NSLog()`:
  * `[pirateParrot appendString:deadMen];`
  * `NSLog(@"%@", pirateParrot);`
  * Run the program with `⌘``R`, this will print `Dead men`.
5. Then, append `tell` and `noTales` to `pirateParrot` by calling the `appendFormat:` method on `pirateParrot` and supplying a formatted string that includes a space before `tell`, a space between `tell` and `noTales`, and an exclamation point (`!`) at the end:
  * `[pirateParrot appendFormat:@" %@ %@!", tell, noTales];`
6. Now, print `pirateParrot` to the console again using another `NSLog()`:
  * `NSLog(@"%@", pirateParrot);`
  * Run the program with `⌘``R`, this will print `Dead men tell no tales!`.

At the end of this code-along, your console should print out:

```
Squawk!
squawk
Squawk!
Dead men tell no tales!
Dead men
Dead men tell no tales!
```

#### Code-Along III: [Iago][iago] Is Molting

[iago]: https://en.wikipedia.org/wiki/Iago_(Disney_character)

1. Create two new `NSString` variables called `iagoLook` and `iagoMolting` and respectively set them equal to the lowercase strings `@"look at me"` and `@"i'm molting"`:
  * `NSString *iagoLook = @"look at me";`
  * `NSString *iagoMolting = @"i'm molting";`
2. Print a concatenation of the strings using an `NSLog()`:
  * `NSLog(@"%@ %@", iagoLook, iagoMolting);`
  * Run the program with `⌘``R`, this will print `look at me i'm molting`.
3. Make the strings uppercase by setting the strings equal to a call of the `uppercaseString` method to themselves, then `NSLog()` the strings again like above:
  * `iagoLook = [iagoLook uppercaseString];`
  * `iagoMolting = [iagoMolting uppercaseString];`
  * `NSLog(@"%@ %@", iagoLook, iagoMolting);`
  * Run the program with `⌘``R`, this will print `LOOK AT ME I'M MOLTING`.
3. Create a new `NSString` variable called `iagoShout` and set it equal a call of `NSString`'s `stringWithFormat:` method supplied with a format string with two object format specifiers separated by a space and ending with an `!` ("exclamation point"), and the arguments `iagoLook` and `iagoMolting`, then print `iagoShout` using an `NSLog()`:
  * `NSString *iagoShout = [NSString stringWithFormat:@"%@ %@!", iagoLook, iagoMolting];`
  * `NSLog(@"%@", iagoShout);`
  * Run the program with `⌘``R`, this will print `LOOK AT ME I'M MOLTING!`.

At the end of this code-along, your console should print out:

```
Squawk!
squawk
Squawk!
Dead men tell no tales!
Dead men
Dead men tell no tales!
look at me i'm molting
LOOK AT ME I'M MOLTING!
LOOK AT ME I'M MOLTING!
```



