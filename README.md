# ECE750_proj
1. Build ViZDoom
```
cd ViZDoom
mkdir build
cd build
cmake .. -DCMAKE_BUILD_TYPE=Release -DBUILD_PYTHON3=ON -GNinja
```
2. Export ViZDoom so that Arnold can find it
```
export PYTHONPATH=path-to-ViZDoom/build/bin/python3.8/pip_package
```
3. Run Arnold
```
python arnold.py 
  --scenario coverage 
  --wad full_deathmatch 
  --n_bots 8 
  --action_combinations 
  "move_fb;move_lr;turn_lr;attack" 
  --frame_skip 4 
  --game_features "enemy" 
  --network_type dqn_rnn 
  --recurrence lstm 
  --n_rec_updates 5 
  --visualize=True
```
You should be able to see the game open up, run for a while, then closed. Its coverage information at
the end of each episode should be printed to the terminal.

4. Static fuzzing

Included is the whole assignment folder that Arie and I prepared for our course, with a very detailed 
README in it.

Best regards,

Nham
