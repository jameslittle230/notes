Tensorboard requires SSH tunneling to work on the Bowdoin Linux Shared Filesystem thing.

```bash
ssh -L 6006:localhost:6006 dover
```

Then run the web server command, in this case:

```bash
tensorboard --logdir=./object_detection/modeldir
```

but that's not really important for this note.
