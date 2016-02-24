==========================================================================
   Pre-Extracted Image Features for the Animals_with_Attributes Dataset
==========================================================================

Names and IDs of all classes are in the file 
- classes.txt

Predicate names andIDs are in the file
- predicates.txt

Training and test classnames for the attribute-based classifier are in 
- trainclasses.txt, testclasses.txt

The class<->attribute matrix is given in three formats.
- predicate-matrix-numeric.txt (positive numeric entries, some missing 
  entries encoded as -1)
- predicate-matrix-binary.txt (binarized with mean of feature, missing 
  set to 0)
- predicate-matrix.png (PNG image file for visual inspection)

Note that the entries are in the order of the names/predicates files,
*not* alphabetically.

There are 6 feature representations:

- cq: (global) color histogram (1x1 + 2x2 + 4x4 spatial pyramid, 128 bins 
      each, each histogram L1-normalized)
- lss[1]: local self similarity (2000 entry codebook, raw bag-of-visual-word 
          counts)
- phog[2]: histogram of oriented gradients (1x1 + 2x2 + 4x4 spatial pyramid, 
           12 bins each, each histogram L1-normalized or all zero)
- rgsift[3]: rgSIFT descriptors (2000 entry codebook, bag-of-visual-word counts, 
             L1-normalized)
- sift[4]: SIFT descriptors (2000 entry codebook, raw bag-of-visual-word counts)
- surf[5]: SUFT descriptors (2000 entry codebook, raw bag-of-visual-word counts)

Each file consists of one sample per line in ASCII format.
All representations have non-negative entries. 

-----------------------------------------------------------------
      Instructions for fixed-split Attribute-Based Classification
-----------------------------------------------------------------

- train using all examples of all 40 classes from "trainclasses.txt"
- test on all examples of 10 classes specified in the "testclasses.txt"

-----------------------------------------------------------------
      Instructions for CV-like Multi-Class Classification
-----------------------------------------------------------------

Follow a protocol similar to Caltech256: 
- choose N_train \in {5,10,15,20,25,30,40,50} and set N_test=25
- train on N_train random training examples from each class
- test on N_test random examples out of the remaining images 
  from each class 
- calculate the mean of the confusion matrix (class averaged accuracy)
- report averaged results for 10-times this procedure

-----------------------------------------------------------------
      References
-----------------------------------------------------------------

[1] E. Shechtman, and M. Irani: "Matching Local Self-Similarities 
    across Images and Videos", CVPR 2007.

[2] A. Bosch, A. Zisserman, and X. Munoz: "Representing shape with 
    a spatial pyramid kernel", CIVR 2007.

[3] Koen E. A. van de Sande, Theo Gevers and Cees G. M. Snoek:
    "Evaluation of Color Descriptors for Object and Scene 
    Recognition", CVPR 2008.

[4] D. G. Lowe, "Distinctive Image Features from Scale-Invariant 
    Keypoints", IJCV 2004.
    
[5] H. Bay, T. Tuytelaars, and L. Van Gool: "SURF: Speeded Up 
    Robust Features", ECCV 2006. 
