page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.losses.absolute_difference


<table class="tfo-notebook-buttons tfo-api" align="left">

<td>
  <a target="_blank" href="https://github.com/tensorflow/tensorflow/blob/r1.15/tensorflow/python/ops/losses/losses_impl.py#L206-L256">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td></table>



Adds an Absolute Difference loss to the training procedure.

### Aliases:

* <a href="/api_docs/python/tf/losses/absolute_difference"><code>tf.compat.v1.losses.absolute_difference</code></a>


``` python
tf.losses.absolute_difference(
    labels,
    predictions,
    weights=1.0,
    scope=None,
    loss_collection=tf.GraphKeys.LOSSES,
    reduction=Reduction.SUM_BY_NONZERO_WEIGHTS
)
```



<!-- Placeholder for "Used in" -->

`weights` acts as a coefficient for the loss. If a scalar is provided, then
the loss is simply scaled by the given value. If `weights` is a `Tensor` of
shape `[batch_size]`, then the total loss for each sample of the batch is
rescaled by the corresponding element in the `weights` vector. If the shape of
`weights` matches the shape of `predictions`, then the loss of each
measurable element of `predictions` is scaled by the corresponding value of
`weights`.

#### Args:


* <b>`labels`</b>: The ground truth output tensor, same dimensions as 'predictions'.
* <b>`predictions`</b>: The predicted outputs.
* <b>`weights`</b>: Optional `Tensor` whose rank is either 0, or the same rank as
  `labels`, and must be broadcastable to `labels` (i.e., all dimensions must
  be either `1`, or the same as the corresponding `losses` dimension).
* <b>`scope`</b>: The scope for the operations performed in computing the loss.
* <b>`loss_collection`</b>: collection to which this loss will be added.
* <b>`reduction`</b>: Type of reduction to apply to loss.


#### Returns:

Weighted loss float `Tensor`. If `reduction` is `NONE`, this has the same
shape as `labels`; otherwise, it is scalar.



#### Raises:


* <b>`ValueError`</b>: If the shape of `predictions` doesn't match that of
  `labels` or if the shape of `weights` is invalid or if `labels`
  or `predictions` is None.



#### Eager Compatibility
The `loss_collection` argument is ignored when executing eagerly. Consider
holding on to the return value or collecting losses via a <a href="../../tf/keras/Model"><code>tf.keras.Model</code></a>.