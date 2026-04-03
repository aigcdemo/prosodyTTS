The internal LLM of the target
TTS system is fine-tuned to interpret the prosodic markers injected
from Stage 1 and condition its acoustic token generation on these explicit instructions. Specifically, the model learns to map the discrete,
symbolic marker sequences—which encode precise, time-aligned
prosodic targets such as pitch contours, duration, and energy—to
the corresponding latent acoustic representations. This fine-tuning
establishes a deterministic instruction-to-markers-to-acoustics
pathway: high-level user descriptions are first translated into finegrained markers, which then serve as intermediate, interpretable
control signals to guide the synthesis of expressive and temporally accurate speech, without modifying the core architecture or
compromising the naturalness of the base TTS model.

** Metadata corresponding to Voxbox will be provided here **
