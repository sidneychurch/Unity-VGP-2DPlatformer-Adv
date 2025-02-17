# Title Screen
---

If you haven't already, rename the default scene from SampleScene to something like LevelOne

Right-click, Create > Scene > Scene

![img.png](img.png)

Name the new scene something like StartScreen

Double-click StartScreen to load it.

Add a UI Legacy Button
Rename it to PlayBtn and make the text on the button say Play

Do the same thing for two more buttons, but make them About and Quit

Create an empty object called Buttons and place the buttons inside

Arrange the buttons so that they align vertically.

![img_1.png](img_1.png)

Create a new script in the Scripts folder and name it StartBtns

Open it

First let's look at how we can load a scene.

>[!NOTE]
> Remember, scenes can be thought of as just game levels.

## Play
---
I want to make it so that when I press (or click) on the Play button we load the first level of the game. In order to do that,
Unity has a built-in class called SceneManager, but first we need to include it by adding:

![img_2.png](img_2.png)

Now I want to create a function to call when I click on the Play button, so I'm going to create a new function named PlayGame():

![img_3.png](img_3.png)

Save the script and head back to Unity.

First add the StartBtns script to the Buttons object that contains our three menu buttons.

![img_5.png](img_5.png)

If you click on PlayBtn and scroll down, you'll see a category named Button. In that category is a place where we can define
what happens when the button is pressed, named _On Click()_:

![img_4.png](img_4.png)

You can have multiple things happen when you click on a button, but we just want to call the one function we made. Click on 
the + button to add an event to trigger when the button is clicked:

![img_6.png](img_6.png)

Where it says None, we need to add a reference to an object. Since our Buttons object contains the script with the function
we want to call, that's what we'll reference. You can just drag Buttons from the Hierarchy and drop it in that area. You should see the
Buttons object displayed, and when you click on the dropdown that says No Function, you'll see a list of things we can do relating to the Buttons object.
You should notice that the name of the script we added, StartBtns, is also an option.

![img_7.png](img_7.png)

Looking through the options of StartBtn, you'll see that our PlayGame function isn't listed. There's good reason for that. We've talked about private and
public variables in class, where if we want to be able to set the reference of make the variable available in the editor, then we make it public. The same goes for 
functions. If you want to be able to call a function from a button click, we want to make the function public. If you go back and make this one change:

![img_8.png](img_8.png)

Save it and look at our options again:

![img_9.png](img_9.png)

Now we can choose PlayGame() as a function to call.

![img_10.png](img_10.png)

Now if you play the game, you should be able to test it out:

![playBtn.gif](playBtn.gif)

## Quit
---
Let's tackle another easy one. I want to make it so that when I click the Quit button, the game exits. This really only works if we actually build
the project into a proper application, but I want to mimic the functionality when I test in the editor as well. To do that, we need to first add:

![img_11.png](img_11.png)

Then I'll make a new function to call:

![img_12.png](img_12.png)

Now call QuitGame when you press the Quit button. If you test it, you'll see that the editor stops playing the game.

## About
---
For the last button, I want to have a text panel display that explains what the narrative of the game is about. If you're making prototypes or just small games where
you don't have the time or resources to develop a full game to explain your story, it's good to have an about section that lets the player understand the world they're
about to enter.

I'm going to start off by creating a new Panel object inside my canvas: right-click > UI > Panel

![img_13.png](img_13.png)

Next I want to Resize the panel to something like this (I'm just guessing at the moment):

![img_14.png](img_14.png)

Next I want to add a Button and a text element to the panel. Then I'll rename them so it looks likes this:

![img_15.png](img_15.png)

Then resize and place the button, along with the text:

![img_16.png](img_16.png)

To see everything, I temporarily disabled the Buttons object. I typed out my text, made it bigger for visibility, and decided to move my close button:

![img_17.png](img_17.png)

With Buttons visible, everything is hard to read

![img_18.png](img_18.png)

What I would like happen after clicking the about button is to display the panel and hide Buttons. Then do the opposite when the closed button is clicked.
Neat thing is, we can do all of that without coding.

We'll add two events to happen for About's On Click():
> Buttons > GameObject > SetActive > false

![img_19.png](img_19.png)

Then we want to make the Panel's active state true:

![img_20.png](img_20.png)

Now we want to set this up to do the opposite when we click the close button in the panel:

![img_21.png](img_21.png)

Now for the Panel object, let's uncheck it so that it starts off not active:

![img_22.png](img_22.png)

Now if you test it, you should be flipping back and forth between the panel and the button objects:

![about.gif](about.gif)

Now I'm going to add another panel for a background, some images (which are using sprites), and a title just to make it more title-ly:

![img_23.png](img_23.png)

---
>Next: [Make Some Noise](/02_Sound/SOUND.md)