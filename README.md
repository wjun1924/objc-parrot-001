# Code-Along: Parrot

## Objectives

1. Create variables.
2. Use `NSLog()` to print a formatted string to the console.
3. Change the case of a string with the `uppercaseString` method.
3. Copy a string with the `stringWithString:` method.
4. Concatenate strings with the `stringByAppendingString:` method.
5. Concatenate an interpolated string with the `stringByAppendingFormat:` method.
6. Create a new interpolated string with the `stringWithFormat:` method.

## Instructions

This code-along lab will walk you through creating, manipulating, and concatenating (combining) strings while printing them with `NSLog()`.

Open the `objc-parrot.xcodeproj` file (`$ open objc-parrot.xcodeproj`) and navigate to the `FISAppDelegate.m` implementation file. You'll enter all of your code in the `application:didFinishLaunchingWithOptions:` method body before the `return YES` line.

**Top-tip:** *If you wish to play around with Objective-C code snippets, this location in a blank program (or one of these early labs that we're supplying to you) is the best option for a "playground". Objective-C is not accurately supported by any REPL or by playgrounds like many other programming languages including Swift. It takes a full Xcode project to run code snippets.*

#### Code-Along I: "Squawk!"

##### A. `NSLog()` and the String Literal
1. Print the string `@"Squawk!"` to the console by placing it directly inside an `NSLog()`:
  * `NSLog(@"Squawk!");`  
  * Run the program with `⌘``R`, this will print `Squawk!`.
2. Print the string `@"Squawk!"` by submitting it to an `NSLog()` as an argument for a format string with one specifier:
  * `NSLog(@"%@", @"Squawk!");` 
  *  Run the program with `⌘``R`, this will print another `Squawk!`.
3. Copy the line above, but move the exclamation point (`!`)  from the argument string into the format string:
  * `NSLog(@"%@!", @"Squawk");`
  *  Run the program with `⌘``R`, this will print a third `Squawk!`.
4. Copy the line above, but add a call of the `uppercaseString` method on the argument string `@"Squawk"` so the returned (uppercased) string is interpolated into the `NSLog()`'s format string:
  * `NSLog(@"%@!", [@"Squawk" uppercaseString]);`
  *  Run the program with `⌘``R`, this will print `SQUAWK!`.

##### B. `NSString` Variable
1. Create an `NSString` variable called `squawk` and set it equal to a string literal `@"squawk"` in all lowercase, then submit it to an `NSLog()` as format argument:
  * `NSString *squawk = @"squawk";`
  * `NSLog(@"%@", squawk);`
  * Run the program with `⌘``R`, this will print `squawk`.
2. Now, set the `squawk` string variable equal to a call of the `uppercaseString` method on itself, and print it again:
  * `squawk = [squawk uppercaseString];`
  * `NSLog(@"%@", squawk);`
  * Run the program with `⌘``R`, this will print `SQUAWK`.
3. Now, add an `!` to `squawk` by setting it equal to a call of `stringByAppendingString:` on itself, the print it again:
  * `squawk = [squawk stringByAppendingString:@"!"];`
  * `NSLog(@"%@", squawk);`
  * Run the program with `⌘``R`, this will print `SQUAWK!`.

At the end of this section your console should print out:

```
Squawk!
Squawk!
Squawk!
SQUAWK!
squawk
SQUAWK
SQUAWK!
```

#### Code-Along II: "Wind in yer sails!"

##### A. Interpolate multiple strings into an `NSLog()`
1. Create four `NSString` variables; `wind`, `inString`, `yer`, and `sails`; and set them equal to, respectively, `@"Wind"`, `@"in"`, `@"yer"`, and `@"sails"`:
  * `NSString *wind = @"Wind";`
  * `NSString *inString = @"in";`
  * `NSString *yer = @"yer";`
  * `NSString *sails = @"sails";`
2. Print the four strings using a format string with four specifiers separated by a space, and ending with an exclamation point (`!`):
  * `NSLog(@"%@ %@ %@ %@!", wind, inString, yer, sails);`
  * Run the program with `⌘``R`, this will print `Wind in yer sails!`.

##### B. Interpolate multiple strings into a string variable
1. Create a new `NSString` variable called `windInYerSails` and use it capture the return of calling `stringWithFormat:` on `NSString`. Submit to the method call a format string and format arguments identical to the `NSLog()` above:
  * `NSString *windInYerSails = [NSString stringWithFormat:@"%@ %@ %@ %@!", wind, inString, yer, sails];`
2. Print `windInYerSails` to the console:
  * `NSLog(@"%@", windInYerSails);`
  * Run the program with `⌘``R`, this will print another `Wind in yer sails!`.

##### C. Build a string by concatenating substrings
1. Print the `wind` string by itself:
  * `NSLog(@"%@", wind);`
  * Run the program with `⌘``R`, this will print `Wind`.
2. Reuse `windInYerSails` to capture a call of the `stringWithString:` method on `NSString` with `wind` supplied as the argument string, the print `windInYerSails`:
  * `windInYerSails = [NSString stringWithString:wind];`
  * `NSLog(@"%@", windInYerSails);`
  * Run the program with `⌘``R`, this will print another `Wind`.
3. Call the `stringByAppendingString:` method on `windInYerSails` with a string literal containing a space (`@" "`) as the argument:
  * `windInYerSails = [windInYerSails stringByAppendingString:@" "];`
4. Call the `stringByAppendingString:` method on `windInYerSails` a second time but with `inString` submitted as the argument, then print `windInYerSails`:
  * `windInYerSails = [windInYerSails stringByAppendingString:inString];`
  * `NSLog(@"%@", windInYerSails);`
  * Run the program with `⌘``R`, this will print `Wind in`.
5. Call the `stringByAppendingFormat:` method on `windInYerSails` with a format string containing a space and one format specifier and the `yer` string as the format argument, then print `windInYerSails`:
  * `windInYerSails = [windInYerSails stringByAppendingFormat:@" %@", yer];`
  * `NSLog(@"%@", windInYerSails);`
  * Run the program with `⌘``R`, this will print `Wind in yer`.
6. Call the `stringByAppendingFormat:` method on `windInYerSails` again but now with a format string containing a space, one format specifier, and an exclamation point (`!`) and the `sails` string as the format argument, then print `windInYerSails` again:
  * `windInYerSails = [windInYerSails stringByAppendingFormat:@" %@!", sails];`
  * `NSLog(@"%@", windInYerSails);`
  * Run the program with `⌘``R`, this will print `Wind in yer sails!`.

At the end of this section your console should also print:

```
Wind in yer sails!
Wind in yer sails!
Wind
Wind
Wind in
Wind in yer
Wind in yer sails!
```
*Mostly we figure that means "yes".*

#### Code-Along III: [Iago][iago] Is Molting

[iago]: https://en.wikipedia.org/wiki/Iago_(Disney_character)

##### A.
1. Create five new `NSString` variables; `look`, `at`, `me`, `im`, and `molting`; and set them equal to, respectively; `@"look"`, `@"at"`, `@"me"`, `@"i'm"`, and `@"molting"`.
  * `NSString *look = @"look";`
  * `NSString *at = @"at";`
  * `NSString *me = @"me";`
  * `NSString *im = @"i'm";`
  * `NSString *molting = @"molting";`
2. Now print the five strings using an `NSLog()` with no characters other than the five required format specifiers:
  * `NSLog(@"%@%@%@%@%@", look, at, me, im, molting);`
  * Run the program with `⌘``R`, this will print `lookatmei'mmolting`.
3. Now print the five strings again but insert a space between each specifier:
  * `NSLog(@"%@ %@ %@ %@ %@", look, at, me, im, molting);`
  * Run the program with `⌘``R`, this will print `look at me i'm molting`.
4. Now print the five strings again but with a comma (`,`) after the third format specifier and an exclamation point (`!`) after the fifth format specifier:
  * `NSLog(@"%@ %@ %@, %@ %@!", look, at, me, im, molting);`
  * Run the program with `⌘``R`, this will print `look at me, i'm molting!`.
5. Lastly, print the five strings again, but call the `uppercaseString` method on each of them within the `NSLog()` itself:
   * `NSLog(@"%@ %@ %@, %@ %@!", [look uppercaseString], [at uppercaseString], [me uppercaseString], [im uppercaseString], [molting uppercaseString]);`
  * Run the program with `⌘``R`, this will print `LOOK AT ME, I'M MOLTING!`.

##### B.
1. Create a new `NSString` variable called `lookAt` and use it capture the return of calling the `stringByAppendingFormat:` method on the `look` string with a format string that has one space and one format specifier and the `at` string as the format argument, then print `lookAt`:
  * `NSString *lookAt = [look stringByAppendingFormat:@" %@", at];`
  * `NSLog(@"%@", lookAt);`
  * Run the program with `⌘``R`, this will print `look at`.
2. Create a new `NSString` variable called `lookAtMe` and use to capture the return of calling the `stringByAppendingFormat:` method on the `lookAt` string with a format string that has one space and one format specifier and the `me` string as the format argument, then print `lookAtMe`:
  * `NSString *lookAtMe = [lookAt stringByAppendingFormat:@" %@", me];`
  * `NSLog(@"%@", lookAtMe);`
  * Run the program with `⌘``R`, this will print `look at me`.
3. Use `lookAtMe` to capture the return of calling `uppercaseString` on `lookAtMe` (itself), then print `lookAtMe`:
  * `lookAtMe = [lookAtMe uppercaseString];`
  * `NSLog(@"%@", lookAtMe);`
  * Run the program with `⌘``R`, this will print `LOOK AT ME`.
4. Create a new `NSString` variable called `imMolting` and set it a call on `NSString` of the `stringWithFormat:` method supplied with a format string with two format specifiers separated by a space and the `im` string and `molting` strings as the format arguments, then print `imMolting`:
  * `NSString *imMolting = [NSString stringWithFormat:@"%@ %@", im, molting];`
  * `NSLog(@"%@", imMolting);`
  * Run the program with `⌘``R`, this will print `i'm molting`.
5. Use `imMolting` to capture the return of calling `uppercaseString` on `imMolting` (itself), then print `imMolting`:
  * `imMolting = [imMolting uppercaseString];`
  * `NSLog(@"%@", imMolting);`
  * Run the program with `⌘``R`, this will print `I'M MOLTING`.
6. Create a new `NSString` variable called `lookAtMeImMolting` and use to capture the return of calling `stringByAppendingFormat:` on `lookAtMe`. Supply the format argument with a format string containing a comma (`,`), a space, one format specifier, and an exclamation point (`!`) and `imMolting` as the format argument, the print `lookAtMeImMolting`:
  * `NSString *lookAtMeImMolting = [lookAtMe stringByAppendingFormat:@", %@!", imMolting];`
  * `NSLog(@"%@", lookAtMeImMolting);`
  * Run the program with `⌘``R`, this will print `LOOK AT ME, I'M MOLTING!`.

##### C.
1. Create a new `NSString` variable called `iagoShout` and set it equal to a call on `NSString` of the `stringWithFormat:` method with a format string with five format specifiers matching the last `NSLog()` from part A, and the five word strings as the format arguments:
  * `NSString *iagoShout = [NSString stringWithFormat:@"%@ %@ %@, %@ %@!", look, at, me, im, molting];`
  * `NSLog(@"%@", iagoShout);`
  * Run the program with `⌘``R`, this will print `look at me, i'm molting!`.
2. Now, print a call of `uppercaseString` on `iagoShout`:
  * `NSLog(@"%@", [iagoShout uppercaseString]);`
  * Run the program with `⌘``R`, this will print `LOOK AT ME, I'M MOLTING!`.
3. Use `iagoShout` to capture the return of calling `uppercaseString` on `iagoShout` (itself), then print `iagoShout`:
  * `iagoShout = [iagoShout uppercaseString];`
  * `NSLog(@"%@", iagoShout);`
  * Run the program with `⌘``R`, this will print another `LOOK AT ME, I'M MOLTING!`.

At the end of this code-along, your console should print out:

```
lookatmei'mmolting
look at me i'm molting
look at me, i'm molting!
LOOK AT ME, I'M MOLTING!
look at
look at me
LOOK AT ME
i'm molting
I'M MOLTING
LOOK AT ME, I'M MOLTING!
look at me, i'm molting!
LOOK AT ME, I'M MOLTING!
LOOK AT ME, I'M MOLTING!
```




<a href='https://learn.co/lessons/objc-parrot' data-visibility='hidden'>View this lesson on Learn.co</a>
