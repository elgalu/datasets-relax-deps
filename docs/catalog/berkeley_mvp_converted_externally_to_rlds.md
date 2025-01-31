<div itemscope itemtype="http://schema.org/Dataset">
  <div itemscope itemprop="includedInDataCatalog" itemtype="http://schema.org/DataCatalog">
    <meta itemprop="name" content="TensorFlow Datasets" />
  </div>
  <meta itemprop="name" content="berkeley_mvp_converted_externally_to_rlds" />
  <meta itemprop="description" content="xArm performing 6 manipulation tasks&#10;&#10;To use this dataset:&#10;&#10;```python&#10;import tensorflow_datasets as tfds&#10;&#10;ds = tfds.load(&#x27;berkeley_mvp_converted_externally_to_rlds&#x27;, split=&#x27;train&#x27;)&#10;for ex in ds.take(4):&#10;  print(ex)&#10;```&#10;&#10;See [the guide](https://www.tensorflow.org/datasets/overview) for more&#10;informations on [tensorflow_datasets](https://www.tensorflow.org/datasets).&#10;&#10;" />
  <meta itemprop="url" content="https://www.tensorflow.org/datasets/catalog/berkeley_mvp_converted_externally_to_rlds" />
  <meta itemprop="sameAs" content="https://arxiv.org/abs/2203.06173" />
  <meta itemprop="citation" content="@InProceedings{Radosavovic2022,&#10;  title = {Real-World Robot Learning with Masked Visual Pre-training},&#10;  author = {Ilija Radosavovic and Tete Xiao and Stephen James and Pieter Abbeel and Jitendra Malik and Trevor Darrell},&#10;  booktitle = {CoRL},&#10;  year = {2022}&#10;}" />
</div>

# `berkeley_mvp_converted_externally_to_rlds`


Note: This dataset was added recently and is only available in our
`tfds-nightly` package
<span class="material-icons" title="Available only in the tfds-nightly package">nights_stay</span>.

*   **Description**:

xArm performing 6 manipulation tasks

*   **Homepage**:
    [https://arxiv.org/abs/2203.06173](https://arxiv.org/abs/2203.06173)

*   **Source code**:
    [`tfds.robotics.rtx.BerkeleyMvpConvertedExternallyToRlds`](https://github.com/tensorflow/datasets/tree/master/tensorflow_datasets/robotics/rtx/rtx.py)

*   **Versions**:

    *   **`0.1.0`** (default): Initial release.

*   **Download size**: `Unknown size`

*   **Dataset size**: `Unknown size`

*   **Auto-cached**
    ([documentation](https://www.tensorflow.org/datasets/performances#auto-caching)):
    Unknown

*   **Splits**:

Split | Examples
:---- | -------:

*   **Feature structure**:

```python
FeaturesDict({
    'episode_metadata': FeaturesDict({
        'file_path': Text(shape=(), dtype=string),
    }),
    'steps': Dataset({
        'action': Tensor(shape=(8,), dtype=float32),
        'discount': Scalar(shape=(), dtype=float32),
        'is_first': bool,
        'is_last': bool,
        'is_terminal': bool,
        'language_embedding': Tensor(shape=(512,), dtype=float32),
        'language_instruction': Text(shape=(), dtype=string),
        'observation': FeaturesDict({
            'gripper': Scalar(shape=(), dtype=bool),
            'hand_image': Image(shape=(480, 640, 3), dtype=uint8),
            'joint_pos': Tensor(shape=(7,), dtype=float32),
            'pose': Tensor(shape=(7,), dtype=float32),
        }),
        'reward': Scalar(shape=(), dtype=float32),
    }),
})
```

*   **Feature documentation**:

Feature                      | Class        | Shape         | Dtype   | Description
:--------------------------- | :----------- | :------------ | :------ | :----------
                             | FeaturesDict |               |         |
episode_metadata             | FeaturesDict |               |         |
episode_metadata/file_path   | Text         |               | string  | Path to the original data file.
steps                        | Dataset      |               |         |
steps/action                 | Tensor       | (8,)          | float32 | Robot action, consists of [7 delta joint pos,1x gripper binary state].
steps/discount               | Scalar       |               | float32 | Discount if provided, default to 1.
steps/is_first               | Tensor       |               | bool    |
steps/is_last                | Tensor       |               | bool    |
steps/is_terminal            | Tensor       |               | bool    |
steps/language_embedding     | Tensor       | (512,)        | float32 | Kona language embedding. See https://tfhub.dev/google/universal-sentence-encoder-large/5
steps/language_instruction   | Text         |               | string  | Language Instruction.
steps/observation            | FeaturesDict |               |         |
steps/observation/gripper    | Scalar       |               | bool    | Binary gripper state (1 - closed, 0 - open)
steps/observation/hand_image | Image        | (480, 640, 3) | uint8   | Hand camera RGB observation.
steps/observation/joint_pos  | Tensor       | (7,)          | float32 | xArm joint positions (7 DoF).
steps/observation/pose       | Tensor       | (7,)          | float32 | Gripper pose, robot frame, [3 position, 4 rotation]
steps/reward                 | Scalar       |               | float32 | Reward if provided, 1 on final step for demos.

*   **Supervised keys** (See
    [`as_supervised` doc](https://www.tensorflow.org/datasets/api_docs/python/tfds/load#args)):
    `None`

*   **Figure**
    ([tfds.show_examples](https://www.tensorflow.org/datasets/api_docs/python/tfds/visualization/show_examples)):
    Not supported.

*   **Examples**
    ([tfds.as_dataframe](https://www.tensorflow.org/datasets/api_docs/python/tfds/as_dataframe)):
    Missing.

*   **Citation**:

```
@InProceedings{Radosavovic2022,
  title = {Real-World Robot Learning with Masked Visual Pre-training},
  author = {Ilija Radosavovic and Tete Xiao and Stephen James and Pieter Abbeel and Jitendra Malik and Trevor Darrell},
  booktitle = {CoRL},
  year = {2022}
}
```

