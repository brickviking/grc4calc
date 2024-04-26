# Grocery Program for Casio calculator

This program provides a basic grocery calculation program for the FX-9750/9860GII family of calculators. Earlier revisions of this program also worked well (but slowly) on the previous fx-9750G+.

### Transcribing notes
These files all appear on this site just like they do on a calculator, however if you simply copy this text into FA-124, you'll find that several characters won't translate very well, such as the symbols for:

* line-endings (↵)
* assignment (→)
* rectangle symbol (r)
* theta symbol (θ)
* not-equals (≠), this looks slightly different on the Casio 9750G+, with the solidus being reversed.
* "if ... THEN ..." (⇒)
*  imaginary number symbol (𝒊)
* multiply (×)
* divide (÷)

At least for the moment (until I get some more programs working) you'll possibly have to type these in by hand, or convert the rogue characters by hand. Later on, two utility programs will be provided to swap between the two formats.

Now onto the meat of the program.

# The program
GROCERY, hereafter referred to as simply GRC, is a small collection of Casio BASIC programs
to help manage the grocery totals each time you go shopping. The collection includes **GRCAMAIN** (the main program), **GRCBTN** (initial screen creation), **GRCHELP** (the help screens), **GRCLIST** (list entered entries),
and a small selection of other helper programs to go along for the ride. The programs I've listed so far
can be run on their own, the other programs should probably not be run straight from the Programs listing.

## Installation

To install GRC, you'll need a Casio **calculator** (fx-9750G+/9860G+ or later), the **cable** to connect
it to a computer, the **FA-124 program** (a free download from Casio), **Microsoft® Windows®**, and
some **batteries** for your calculator. If you're missing any of these things, GRC may not work well for you. I don't know of any working Linux programs to transfer data.
Additionally, I have no original fx-9750G to try this program on, so your mileage may vary if you can even get this program running on that old a calculator.

% Insert pretty pictures of the bits we'll need.

First, make sure your computer's running, and that you've installed the FA-124 program.
The calculator comes with a cable (serial or USB2) that you can *usually* plug
into your computer, if your computer has the right kind of connector. Plug one end into
the calculator and plug the other end into the computer. If your cable is USB, your calculator
should then prompt you to select the Connection mode, choose **F1** (DataTrans) here.

On the computer, find and start up the FA-124 program, and look for the "Connect" button on the top left of the toolbar. Click this, and
your calculator should connect.

% Need pretty picture of FA-124 with connected calculator

Your manual should tell you how to import the GRC programs into your calculator, so copy them in
and select Disconnect.

% Need better noob-friendly instructions for importing GRCAMAIN.g1m

% Don't forget to disconnect

Once you've finished, you should be able to disconnect from the FA-124 toolbar. After one further setup step, GRC is then good to go.

### Initial setup

Turn on the calculator, hit the **MENU** key, select [B] (or Programs). You'll see a list of
installed programs. Skip down to GRCBTN, hit \b F1. This creates the initial framework of the screen,
and you only have to do this once.

% Main

### Starting

Every time you want to run the main program, select GRCAMAIN from the Program listing, and hit F1 (EXE).
This loads up the main program and shows you the first screen, asking if you wish to
load previously-saved values. If this is your first time, you won't have any, so just
select No in this case. 

% Requests whether to load previously-saved values (Yes/No)


# Main Program

% Screen

## Main screen
Once you've started the program, you'll see the main screen. The left hand side
shows the last entry made, the five categories of groceries, their respective totals
in dollars and cents, and a counter for each category. Underneath that, you'll see the
Grand Total, and the total item count. This Grand Total may or may not include the tax
figure, depending upon your Tax settings in the program.

On the right hand side, you'll see a short list of temporary values---more on that later,
and the currently-applied tax rate, along with the amount of tax calculated. On the lower part of
the screen, you'll see the overall total cost and the overall count of items, and below that, the menu line.

% Pretty picture of whole screen, with highlights of sections

% TODO: provide initial screen, and while-running screen

## Menu bar (F1 - F5)

% Need pretty picture of bottom of screen plus top line of keys including F1-F6

The Menu bar is where most of the action happens, and works very much like the menus
in the calculator; the only differences being the words and lack of decoration.
The **F1** through **F5** keys are used to add entries to categories % yeesh!!
and the **F6** key runs the included GRC Help program. For the Vege and Meat categories,
you'll get asked if you're putting in a count (how many there are) or a weight (how
much does your item weigh). For all the categories, you'll also get asked for the
unit cost (per KG if you supplied weight in the previous step).

Once you've provided the price per item, you'll be taken back to the main program with your entry added to the list of items bought.

### Deletion of last entry

Sometimes you might have put in the wrong price, or put in the wrong number of items. In this case, hit the **[DEL]** key. This will remove the last item you entered in from the list. You can then select the correct details.

% Need pretty picture here describing GRCITEM/GRCWGT usage

### Help (F6)
This is a complete though concise explanation of program functions. The usual menu
is on the bottom, and the help program has a complete list of contents (over two pages),
followed by individual help pages for each major function. The one wrinkle with the
Help program contents is that you need to choose a section by number, not by Function key.
To leave the Help, simply choose {\bf Exit} (F1) from the menu. To page forward through
the help, use {\bf Next} (F4), to page backwards, use {\bf Back} (F3), and to skip back
to the Contents, hit F6 on any help page.

% Functions

## Functions (**[MENU]**)

Hitting the **[MENU]** key will take you to a short set of functions.

% Prefs
### Preferences Menu

% Tax
### Tax Menu
As such, this program calculates one tax rate for everything you enter in; it takes no
account of items that are taxed differently or perhaps not at all. Additionally, there
are two ways to show the tax, either the grand total includes the tax as it would do in
the European Union, Great Britain, Australia, New Zealand and similar countries, or it
is calculated separately and *added* to the category total. For example in New Zealand,
the tax rate is 15 % of the total price, and the ticket price at the time of purchase is
the only amount you will pay. In America the tax is calculated additionally to the shelf
price, and consumers are required to pay some additional forms of tax depending upon where
they live. This can mean a significant difference between the shelf price of an item and
the till price. Table 1 shows an example of three common items and their respective
totals at the till.

|Item| Ticket Price (NZD) | (USD)| Total (NZD) | (USD)|
|-|--:|--:|--:|--:|
| Apples | 3.95 | 1.75 | 3.95 | 2.38 |
| Shoes | 129.99 | 59.99 | 129.99 | 65.42 |
| Car | 11995.00 | 5995.00 | 11995.00 | 7377.52 |

\caption{Comparing shelf and till prices.}

### Erase
Removes all entries from the list of items, and allows you to also remove all temporary values.

### Store
Saves a copy of the current list of items to the calculator so you can restore it at a later time or date. 

### Load
This loads a copy of the last-saved list of items. This can be useful when you want to have a grand total, but want to turn the calculator off for a while in between.

### List

This will (at least on the fx-9860GII) show a paged list of the individual items entered, and you can go forward or backward through the list.

# Conclusions

To my knowledge, this is the only program of its type listed at casiopeia.net,
and is a good chance to exercise the power of this calculator. At least in this
country, a lot of school attendees get told to buy them so they can complete
mathematical studies; after they leave school they never really seem to use them
again. I've definitely got a reason to give these calculators a second life.


 
