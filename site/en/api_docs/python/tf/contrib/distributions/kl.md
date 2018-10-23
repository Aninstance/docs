

page_type: reference


<!-- DO NOT EDIT! Automatically generated file. -->
# tf.contrib.distributions.kl

### `tf.contrib.distributions.kl`

``` python
kl(
    dist_a,
    dist_b,
    allow_nan_stats=True,
    name=None
)
```



Defined in [`tensorflow/contrib/distributions/python/ops/kullback_leibler.py`](https://www.github.com/tensorflow/tensorflow/blob/r1.1/tensorflow/contrib/distributions/python/ops/kullback_leibler.py).

See the guide: [Statistical Distributions (contrib) > Kullback-Leibler Divergence](../../../../../api_guides/python/contrib.distributions#Kullback_Leibler_Divergence)

Get the KL-divergence KL(dist_a || dist_b).

If there is no KL method registered specifically for `type(dist_a)` and
`type(dist_b)`, then the class hierarchies of these types are searched.

If one KL method is registered between any pairs of classes in these two
parent hierarchies, it is used.

If more than one such registered method exists, the method whose registered
classes have the shortest sum MRO paths to the input types is used.

If more than one such shortest path exists, the first method
identified in the search is used (favoring a shorter MRO distance to
`type(dist_a)`).

#### Args:

* <b>`dist_a`</b>: The first distribution.
* <b>`dist_b`</b>: The second distribution.
* <b>`allow_nan_stats`</b>: Python `bool`, default `True`. When `True`,
    statistics (e.g., mean, mode, variance) use the value "`NaN`" to
    indicate the result is undefined. When `False`, an exception is raised
    if one or more of the statistic's batch members are undefined.
* <b>`name`</b>: Python `str` name prefixed to Ops created by this class.


#### Returns:

  A Tensor with the batchwise KL-divergence between dist_a and dist_b.


#### Raises:

* <b>`NotImplementedError`</b>: If no KL method is defined for distribution types
    of dist_a and dist_b.