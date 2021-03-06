# Tr
This is a top-down isometric style shooter game
You are a boy who is
having a dream that all of his toys have come to life.
You run around, you shoot zombie teddies and other things,
score points and eventually meet your demise.
So that's what we're going to make
and we're going to be learning about the editor
from putting together a scene
implementing animated characters, AI,
some of the new UI and lots of other stuff.
It's a very uplifting game,
you can't win, you can only eventually lose.
So that's the way we prefer to make them.
The very first thing you'll notice is that on my screen
I have the project open.
We don't want you to have the project open
at all, what we want you to do is to
make your own new scene and we're going to
put this project together.
So if anyone has got the scene open
we don't want you to do that, we want you to make
a brand new scene.
So first of all we're going to go to File - New Scene.
Then what we want you guys to do, to make sure that
everyone's kind of on the same page we're going to ask
you to setup the editor in the same
style that we have.
If you're comfortable with Unity, if you've used Unity before
and you prefer to work in your layout
of the editor that's totally cool, you can keep that.
But if you're new to Unity what we'd like you to do
is to choose the layout menu in the upper right
and choose 2 by 3.
So layout drop down in the upper right and choose 2 by 3.
That would get you a style that gets you something like this.
Then what we'd like you to do is to drag the project panel
and drop it below the hierarchy.
You'll note that when you drag the title tabs
of the panels around they will dock
in to different spaces.
Drop that below the hierarchy
and then you can just drag up the division between those two,
maybe drag this over a little
and then you should be all set.
So hopefully everyone's got a view like that?
Then what I usually like to do is
with the project panel, because we don't really need
to use the thumbnails particularly
there's a slider at the bottom
which will change to list view when dragged
all the way over to the left.
So if we drag it over to the left you're going to see
exactly the same as what I have
on my screen here.
We are working with Unity 4.6
but right now what we'd like you to do is to go to
File - Save Scene As
and we will ask you to put this in
to the Scenes folder.
We don't want you to use the completed
assets version of anything
just use the
Scenes folder that's in the
root of the project.
And we're going to call this Level 01.
So save it as Level 01 in the Scenes folder.
When you've done that successfully you should see the name of
your scene up at the top of the interface.
Okay so the next thing we're going to do is
setup the environment, so I'm just going to show you that first.
So a prefab, just to reiterate
how this stuff works, a prefab is our way of
providing or saving a game object
in to the project.
You can do that for a number of different reasons
and we'll be saving prefabs in order to
spawn them in to the game later with the enemies.
But for the purpose of the environment
we prepared the model
and a number of collider and other elements.
If you look in the prefabs folder you will
find a prefab called environment.
Prefabs are represented by this blue cube icon.
All you need to do is to drag and drop that up
in to the hierarchy.
So just to remind you, the hierarchy and the scene
are intrinsically linked, anything that's in the scene
is therefore in the hierarchy and visa versa.
Just make sure that you've got a decent view of this level.
You can use the hand tool of course
up in the upper left
and use Control to zoom in and out
and Alt to rotate around.
We don't need to worry too much about the view
that you're looking at in the scene view
because we're going to setup the camera to look at
particular part of that later.
What we're just going to check is that we
positioned the environment at the origin.
So with the environment selected in the transform
component you should see the position is at
(0, 0, 0).
If it's not just fill that in, (0, 0, 0)
or go to the cog icon in the
upper right and choose Reset Position.
Then once we've done that we are also going to drag
in the Lights prefab.
Lights is in the prefabs folder,
you simply need to drag that in to
the scene and it should light your scene.
With the lights we don't need to worry about
positioning particularly because it's directional lights.
With directional lights you only need to worry about the rotation.
So if I just show you those briefly you can see that these
directional lights are pointing in
certain rotations and they're going to affect
anything in the scene, you don't need to worry about
where they're positioned.
The way this game is going to work is
we're going to have a camera that's
looking down on the scene.
And what we need to do in order to track
the player around and also to be able to
shoot is to use something called
a ray cast which is going to create an
invisible line from the camera to the floor.
But we've got a very inconsistent floor,
we've got a number of different environment objects
such as these stools, the Lego bricks,
the broken train
and all these different things, so we don't want to worry about
ray casting on to those at different heights
so to make things a lot simpler
what we're doing is we're going to add
in a plane quad.
So what I'd like you guys to do is to go to Game Object
3D Object and Quad.
What you'll notice is this creates a very small
1 by 1 quad right in the centre
of your game.
We're going to reset that to (0,0,0)
in the transform component
so make sure the position of your quad is at 0.
And we're going to rotate it by
90 degrees in the X axis.
Finally we want this to cover the entire
game level so we're going to
scale this by 100 in X
and 100 in Y.
We're going to name this Floor.
So rename from quad
to Floor.
So the next thing we're going to do is
to make this invisible, obviously you'll notice that it looks
pretty horrendous right now.
We don't want to actually see this.
What we want to do is use the collider,
so the outline of this shape.
We don't want to use this kind of grey for any reason at all.
So a quad is made visible by the
mesh renderer component,
and because we don't want that we're just going to
go ahead and remove it so with the floor selected
click the cog to the right of the mesh renderer
and choose Remove Component.
So with your floor selected go to
the cog icon in the upper right and choose
Remove Component and you should see
that you can then only see the collider outline.
Make sure you remove the mesh renderer,
not the mesh filter or the mesh collider.
Remember you've got Undo if anything goes horrendously wrong
but you should then see that you just have the collider around
the outline of the level, something like that.
Then because we don't want
our ray cast to check for anything
but this quad we're going to use layers.
so a layer is a way of isolating
things like ray casting or lighting for example,
to a particular group.
So with the floor selected
if you click the Layer drop down you should see
that we have a floor layer ready for you.
Choose from the Layer drop down at the top of the
the inspector, Floor.
And then save your scene.
The next thing we're going to do is finish off
our environment by adding some background music.
With sound sources in Unity we can attach
them to any object, it's a component that you
use to apply a clip to or you
use scripting to assign clips to.
We are going to have a separate game
object just to keep things separate and just to
keep them nicely organised.
So I'd like you to go to Game Object - Create Empty
and then rename this Background Music.
Return on the Mac or F2 on the PC
just like your operating system
and rename this Background Music
So we're creating an empty and renaming it Background Music.
Then we can add components to our game objects
to make them do different things.
So we have a component menu up at the top
with a bunch of different categories of things
that you can do to your game object to give it different
behaviour of different functionality.
What we're going to add is an audio source
so we can use this component menu
or we can use the Add Component menu
over on the right in the inspector.
So because the inspector will show you properties of the
game object currently selected we can
go in to here and we want to add an Audio
Audio Source
We don't really want to hear the music
for this game playing
every time you press play in your game
but just to make sure that everyone's worked
we are going to do it once.
So to assign a audio clip
to the audio source we can use the circle select.
We're going to refer to circle select a lot throughout
the day, it's the small nipple-like icon
to the right of the audio clip, and what that will do is pop up
a context window which is going to allow you to
find the file you need.
The file you need is Background Music,
surprisingly enough, and simply closing that window
will assign it to that.
For everyone's sanity uncheck Play On Awake.
We also want the music to loop when we are finished
with the game, we do want it to loop
so uncheck Play On Awake and check Loop.
In the volume in the component there is a slider.
And we can just drag that down to about 0.1.
So that's just to balance it with the other sound effects
we have in the game, and then you can go ahead and
save your scene once more.
That's the end of phase one, setting up the environment.
The next thing we're going to do is look at our player character.
