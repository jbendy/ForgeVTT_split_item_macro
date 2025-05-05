# ForgeVTT_split_item_macro

Please feel free to take this and use/modify as much as you want!

Some background:
I have been frustrated handling giant stacks of items when I need to differentiate them. For instance, I had 100 crossbow bolts and I wanted to dip several of them in poison. But how do I make a stack of poisoned bolts? Normally I would have to remove 10 poisoned bolts from my stack of bolts, then make a new item, set the quantity to 10, set the appropriate weight, and copy the image/description & name of the previous stack, and only then could I modify descriptions to contain the poison information. If you don't find this tedious then this macro is not for you.
I was surprised to find that no one has done this so far in the Forge VTT Discord or the subreddit, and that the macro is not built-in to Forge. There are some inventory modules you can add that will overhaul your inventory system that include this feature, but why would you want to re-arrange your entire inventory system for one feature?

Anyway, **here are instructions on setting up this macro:**
1. Create a new entry on your hotbar by clicking an empty/unused entry
2. Change the name of the entry. This name is how you will call the macro, so use something easy to type. I have called mine "split"
3. Change the **Type** dropdown from **Chat** to **Macro**
4. Paste the code at the bottom of this post into the **Command** section
5. Click **Save Macro**

**How to use the macro:**
1. In your chat section on the right of the webpage, type the following command: `/macro <name of macro> itemName=<name of item you want to split>`
2. In my case, I named the macro "split", and I am splitting the stack of items in my inventory called "Crossbow Bolts" **Note:** this stack does not need to be consumables. It can be literally anything in your inventory
3. In my case, I would type the following into the chat: `/macro split itemName=Crossbow Bolts`
4. Notice how I used a capital "C" and "B" in my item name? This macro is cAsE sEnSiTiVe. You could easily modify it to not be, but I prefer it this way so I don't accidentally split a different stack that happens to have a similar name. Similarly, "itemName" requires a capital "N"!
5. Press Enter on your keyboard

Now once you go into your inventory, you'll see the original stack and a copy with the name slightly modified. For me, the new stack is called "Crossbow Bolts (Copy)" (see figure 3). You could modify the macro to name the new stack the exact same thing; Forge doesn't care if you have multiple item stacks with the same name.

**Some notes on usage:**
- This macro copies every property of the stack; the picture, description, any tags, the system the item was imported from, etc. Everything.
- The quantity of the new stack will be half of the original rounded down (ex: A quantity of 73 becomes 37 on the original and 36 on the new)
- The original stack's quantity will be reduced by the number of items in the new stack
- You must have your actor's token selected before you run the macro. If you have no tokens selected, or if you have more than 1 token selected, you will get an error
- You must type the name of your stack respecting cAsE sEnSiTiViTy. If not, you will get an error (again, you can change this fairly easily; use a different JavaScript compare method)
- If an item with the name you typed in your inventory is not found, you will get an error
- If the item you are trying to split has a quantity fewer than 2, you will get an error
- If you do receive an error, check the console log in your browser! I have many steps being logged by the macro, so you will likely be able to see which step the error occurred at!
