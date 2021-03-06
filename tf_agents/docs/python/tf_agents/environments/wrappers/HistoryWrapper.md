<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf_agents.environments.wrappers.HistoryWrapper" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="batch_size"/>
<meta itemprop="property" content="batched"/>
<meta itemprop="property" content="__enter__"/>
<meta itemprop="property" content="__exit__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="action_spec"/>
<meta itemprop="property" content="close"/>
<meta itemprop="property" content="current_time_step"/>
<meta itemprop="property" content="observation_spec"/>
<meta itemprop="property" content="render"/>
<meta itemprop="property" content="reset"/>
<meta itemprop="property" content="seed"/>
<meta itemprop="property" content="step"/>
<meta itemprop="property" content="time_step_spec"/>
<meta itemprop="property" content="wrapped_env"/>
</div>

# tf_agents.environments.wrappers.HistoryWrapper

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="https://github.com/tensorflow/agents/tree/master/tf_agents/environments/wrappers.py">View
source</a>

## Class `HistoryWrapper`

Adds observation and action history to the environment's observations.

Inherits From:
[`PyEnvironmentBaseWrapper`](../../../tf_agents/environments/wrappers/PyEnvironmentBaseWrapper.md)

<!-- Placeholder for "Used in" -->

<h2 id="__init__"><code>__init__</code></h2>

```python
__init__(
    *args,
    **kwargs
)
```

Initializes a HistoryWrapper.

#### Args:

*   <b>`env`</b>: Environment to wrap.
*   <b>`history_length`</b>: Length of the history to attach.
*   <b>`include_actions`</b>: Whether actions should be included in the history.

## Properties

<h3 id="batch_size"><code>batch_size</code></h3>

<h3 id="batched"><code>batched</code></h3>

## Methods

<h3 id="__enter__"><code>__enter__</code></h3>

<a target="_blank" href="https://github.com/tensorflow/agents/tree/master/tf_agents/environments/py_environment.py">View
source</a>

```python
__enter__()
```

Allows the environment to be used in a with-statement context.

<h3 id="__exit__"><code>__exit__</code></h3>

<a target="_blank" href="https://github.com/tensorflow/agents/tree/master/tf_agents/environments/py_environment.py">View
source</a>

```python
__exit__(
    unused_exception_type,
    unused_exc_value,
    unused_traceback
)
```

Allows the environment to be used in a with-statement context.

<h3 id="action_spec"><code>action_spec</code></h3>

<a target="_blank" href="https://github.com/tensorflow/agents/tree/master/tf_agents/environments/wrappers.py">View
source</a>

```python
action_spec()
```

<h3 id="close"><code>close</code></h3>

<a target="_blank" href="https://github.com/tensorflow/agents/tree/master/tf_agents/environments/wrappers.py">View
source</a>

```python
close()
```

<h3 id="current_time_step"><code>current_time_step</code></h3>

<a target="_blank" href="https://github.com/tensorflow/agents/tree/master/tf_agents/environments/py_environment.py">View
source</a>

```python
current_time_step()
```

Returns the current timestep.

<h3 id="observation_spec"><code>observation_spec</code></h3>

<a target="_blank" href="https://github.com/tensorflow/agents/tree/master/tf_agents/environments/wrappers.py">View
source</a>

```python
observation_spec()
```

<h3 id="render"><code>render</code></h3>

<a target="_blank" href="https://github.com/tensorflow/agents/tree/master/tf_agents/environments/wrappers.py">View
source</a>

```python
render(mode='rgb_array')
```

<h3 id="reset"><code>reset</code></h3>

<a target="_blank" href="https://github.com/tensorflow/agents/tree/master/tf_agents/environments/py_environment.py">View
source</a>

```python
reset()
```

Starts a new sequence and returns the first `TimeStep` of this sequence.

Note: Subclasses cannot override this directly. Subclasses implement _reset()
which will be called by this method. The output of _reset() will be cached and
made available through current_time_step().

#### Returns:

A `TimeStep` namedtuple containing: step_type: A `StepType` of `FIRST`. reward:
0.0, indicating the reward. discount: 1.0, indicating the discount. observation:
A NumPy array, or a nested dict, list or tuple of arrays corresponding to
`observation_spec()`.

<h3 id="seed"><code>seed</code></h3>

<a target="_blank" href="https://github.com/tensorflow/agents/tree/master/tf_agents/environments/wrappers.py">View
source</a>

```python
seed(seed)
```

<h3 id="step"><code>step</code></h3>

<a target="_blank" href="https://github.com/tensorflow/agents/tree/master/tf_agents/environments/py_environment.py">View
source</a>

```python
step(action)
```

Updates the environment according to the action and returns a `TimeStep`.

If the environment returned a `TimeStep` with
<a href="../../../tf_agents/trajectories/time_step/StepType.md#LAST"><code>StepType.LAST</code></a>
at the previous step the implementation of `_step` in the environment should
call `reset` to start a new sequence and ignore `action`.

This method will start a new sequence if called after the environment has been
constructed and `reset` has not been called. In this case `action` will be
ignored.

Note: Subclasses cannot override this directly. Subclasses implement _step()
which will be called by this method. The output of _step() will be cached and
made available through current_time_step().

#### Args:

*   <b>`action`</b>: A NumPy array, or a nested dict, list or tuple of arrays
    corresponding to `action_spec()`.

#### Returns:

A `TimeStep` namedtuple containing: step_type: A `StepType` value. reward: A
NumPy array, reward value for this timestep. discount: A NumPy array, discount
in the range [0, 1]. observation: A NumPy array, or a nested dict, list or tuple
of arrays corresponding to `observation_spec()`.

<h3 id="time_step_spec"><code>time_step_spec</code></h3>

<a target="_blank" href="https://github.com/tensorflow/agents/tree/master/tf_agents/environments/py_environment.py">View
source</a>

```python
time_step_spec()
```

Describes the `TimeStep` fields returned by `step()`.

Override this method to define an environment that uses non-standard values for
any of the items returned by `step()`. For example, an environment with
array-valued rewards.

#### Returns:

A `TimeStep` namedtuple containing (possibly nested) `ArraySpec`s defining the
step_type, reward, discount, and observation structure.

<h3 id="wrapped_env"><code>wrapped_env</code></h3>

<a target="_blank" href="https://github.com/tensorflow/agents/tree/master/tf_agents/environments/wrappers.py">View
source</a>

```python
wrapped_env()
```
