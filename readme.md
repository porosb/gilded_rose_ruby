## Gilded Rose Refactoring Kata

More info about this Kata [here](https://github.com/emilybache/GildedRose-Refactoring-Kata).

### Simplified Specification

Items properties:
* Name denotes the Class which the item belongs to
* SellIn denotes the number of days in which item should be sold
* Quality denotes the value of item

Items Classes:
* AgedBrie
* BackstagePasses
* Regular
* Sulfuras
* Conjured

Properties features:
* The Quality is always positive and can't be more than 50 (Sulfuras Quality is always 80 and SellIn is endless)
* The Quality decreases by 1 every day 
  * AgedBrie Quality increases the older it gets but it still can't be more than 50
  * BackstagePasses Quality: 
    * grows by 2 when SellIn <= 10
    * grows by 3 when SellIn <= 5
    * Equals 0 when SellIn = 0 
* The SellIn decreases by 1 every day as well
* When SellIn <= 0, the quality degrades by 2 

You should refactor the existing God method #update_quality and add logic for the Conjured Items.

Conjured Items properties:
* The Quaity increases by 2 every day
* When SellIn <=0, the quality degrades by 4

You're not allowed to alter Item class or Items property.

### Result

I've isolated items using single responsibility classes and used Factory pattern to instantiate those specific items.

The code is written by TDD with RSpec and linted by Rubocop.
The [terminal-table gem](https://github.com/tj/terminal-table) is used for output.

![Gilded Rose Table](https://i.imgur.com/RnYHT3F.png)
