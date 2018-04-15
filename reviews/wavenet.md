# [WAVENET: A GENERATIVE MODEL FOR RAW AUDIO](https://arxiv.org/pdf/1609.03499.pdf)

## Summary
* WaveNet is a deep generative model of audio data that operates directly at the waveform level. 
* It was inspired by PixelCNN. 
* They  are autoregressive and combine causal filters with dilated convolutions to allow their receptive fields to grow exponentially with depth, which is important to model the long-range temporal dependencies in audio signals

#### Dilated causal convolutions:
* **Causal convolutions:** The prediction p (xt+1 | x1, ..., xt) emitted by the model at timestep t cannot depend on any of the future timesteps xt+1, xt+2, . . . , xT (Drawback: they require many layers, or large filters to increase the receptive field (= #layers + filter length - 1). )
* A dilated convolution is a convolution where the filter is applied over an area larger than its length by skipping input values with a certain step, exponentially increasing the dilation factor results in exponential receptive field growth with depth. 
* GRUs and residual and parameterised skip connections are used throughout the network, to speed up convergence and enable training of much deeper model.
* Experiments on Multi speaker speech generation, TTS, Music generation, speech recognition.

## Strengths
* Very promising results when applied to music audio modeling for solo instruments. 
* Network is trained on raw audio, and is able to pick up subtleties, like non-spoken sounds (e.g. breathings) for speech or instrument noises that you would not get from vocoders or synthesizers.
