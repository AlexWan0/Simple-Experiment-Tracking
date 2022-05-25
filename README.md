### Plotter

```python
# Each Plotter instance represents one plot.
plotter = Plotter() 

# Add new datapoints as keyword arguments.
# Multiple attributes will be plotted as multiple lines on the same plot.
plotter.add(loss=loss, accuracy=accuracy)

# results.png is the default filepath if none is given.
plotter.output(fp="results.png")
```

### Experiment

```python
# Can also set config_file, plot_file, folder during init.
# Add experiment configuration as keyword arguments.
# Creates folder containing experiment information on init.
experiment = Experiment("<experiment name>", batch_size=32, lr=0.001)

# Appends line to log file in experiment folder.
# Can set log_file, log.txt as default.
experiment.log("New line!")

# Logs keyword arguments to log file, prints it to cmd, and plots it (along with historical datapoints).
# Can set log_file, log.txt as default.
# Can disable cmd or plot by setting those arguments to False.
# Can change the cmd print function (e.g. if you want to use tqdm.write) by passing in a function that takes a single argument to cwd_func.
experiment.log_stats(epoch_num, loss=loss, accuracy=accuracy)
```
