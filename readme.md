# Latent Sound Transfer with Music2Latent

This repository demonstrates a workflow inspired by the paper *"Latent Granular Resynthesis using Neural Audio Codecs"* by Nao Tokui et al. The goal is to transfer characteristics of ambient sounds (e.g., ocean waves) onto a source sound (e.g., a guitar) using latent embeddings from Music2Latent.

## Concept Overview

1. **Compute embeddings of reference sounds**: Start with a set of target audio samples, such as ocean waves, and calculate their latent embeddings using Music2Latent.  
2. **Compute embedding of the source sound**: Take your source audio and compute its embedding.  
3. **Compare embeddings**: Compare the source embedding with the embeddings of the reference sounds to find the closest matches. Different similarity metrics (cosine similarity, Euclidean distance, etc.) can be used.  
4. **Reconstruct with decoder**: Use the Music2Latent decoder to reconstruct the source sound, now influenced by the characteristics of the closest reference sounds, effectively “translating” the timbre.  
5. **Result**: The resulting audio preserves the original source content while adopting sonic qualities of the target sound.

**Note:** The codec and the embedding comparison method can be modified to influence the output. 

---

## Diagram


---

## How to Use

1. Replace `source.wav` with your own instrument or voice recording.  
2. Replace or add target sounds to experiment with different timbres. Ideally, having a representative quantity of recordings will better capture the target characteristics. You can also consider data augmentation, but avoid transforming the target sound too much; otherwise, diverse embeddings may be picked, leading to unwanted results.  
3. Try changing the similarity metric or the Music2Latent codec to creatively achieve different results.  
4. Run the workflow to generate new audio files.

**Notes:**  
- The notebook paths are kept intentionally vague, so you may need to adjust them.  
- Without GPU, an acceptable result may take hours of computation.
- Precomputed seawave embeddings are included as a toy example; they are not extensive or fully representative but you can reproduce my results.  

---

## References

- Paper: *Latent Granular Resynthesis using Neural Audio Codecs*  
- Project Lydia (example optimization): [YouTube link to be added]  
- Music2Latent paper and GitHub repository