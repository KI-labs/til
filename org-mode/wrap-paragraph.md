# Wrap a paragraph

In evil mode in Spacemacs, there are two ways to wrap a long line of text or a paragraph to fit into text width properly. The first way is a Vim way: `g q a p` in normal mode or `g q` in visual mode. The second is emacs way: `M-q`. The difference between the two is invisible when it's just a paragraph but is clearly visible in, for example, plain lists.

Original:

```org
- They change their methods of grasping their phone without realizing it, which also means people cannot observe themselves well enough to predict this behavior.
- 75% of users touch the screen only with one thumb.
- Fewer than 50% of users hold their phone with one hand.
- 36% of users cradle their phone, using their second hand for both greater reach and stability.
- 10% of users hold their phone in one hand and tap with a finger of the other hand.
```

`g q a p` at any point within the list keeps it without change:

```org
- They change their methods of grasping their phone without realizing it, which also means people cannot observe themselves well enough to predict this behavior.
- 75% of users touch the screen only with one thumb.
- Fewer than 50% of users hold their phone with one hand.
- 36% of users cradle their phone, using their second hand for both greater reach and stability.
- 10% of users hold their phone in one hand and tap with a finger of the other hand.
```

`M-q` at any point within the list wraps the item, so selecting the whole list in visual mode and doing `M-q` wraps every item separately, giving exactly the result that is expected:

```org
- They change their methods of grasping their phone without realizing it,
  which also means people cannot observe themselves well enough to predict
  this behavior.
- 75% of users touch the screen only with one thumb.
- Fewer than 50% of users hold their phone with one hand.
- 36% of users cradle their phone, using their second hand for both greater
  reach and stability.
- 10% of users hold their phone in one hand and tap with a finger of the
  other hand.
```

And because `M-q` is a shortcut to an emacs command ["fill-paragraph"](https://www.emacswiki.org/emacs/FillParagraph) and therefore gets executed in any mode.
