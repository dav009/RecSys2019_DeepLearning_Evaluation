# DeepLearning RS Evaluation

## Compilation and experiments
Instructions on how to install and run the experiments are accessible [HERE](README.md).


## Full results
http://pandoc.org/try/


* [SIGIR: Collaborative Memory Networks](#SIGIR-Collaborative-Memory-Networks)
* [RecSys: Spectral Collaborative Filtering](#RecSys-Spectral-Collaborative-Filtering)
* [KDD: Leveraging Meta-path based Context for Top-N Recommendation with a NeuralCo-Attention Model](#KDD-Leveraging-Meta-path-based-Context-for-Top-N-Recommendation-with-a-NeuralCo-Attention-Model)
* [KDD: Collaborative Variational Autoencoder for Recommender Systems](#KDD-Collaborative-Variational-Autoencoder-for-Recommender-Systems)
* [KDD: Collaborative Deep Learning](#KDD-Collaborative-Deep-Learning)
* [WWW: Neural Collaborative Filtering](#WWW-Neural-Collaborative-Filtering)
* [WWW: Variational Autoencoders for Collaborative Filtering](#WWW-Variational-Autoencoders-for-Collaborative-Filtering)






### SIGIR: Collaborative Memory Networks



| citeulike  |    HR@5    |   NDCG@5   |   HR@10    |  NDCG@10   |
| :--------- | :--------: | :--------: | :--------: | :--------: |
| Random     |   0.0562   |   0.0332   |   0.1007   |   0.0474   |
| TopPop     |   0.1803   |   0.1220   |   0.2783   |   0.1535   |
| UserKNN CF | **0.8213** | **0.7033** | **0.8935** | **0.7268** |
| ItemKNN CF | **0.8116** | **0.6939** |   0.8878   | **0.7187** |
| P3alpha    | **0.8202** | **0.7061** |   0.8901   | **0.7289** |
| RP3beta    | **0.8226** | **0.7114** | **0.8941** | **0.7347** |
| PureSVD    |   0.7056   |   0.5807   |   0.7892   |   0.6079   |
| CMN        |   0.8069   |   0.6666   |   0.8910   |   0.6942   |


|  Epinions          |    HR@5    |   NDCG@5   |   HR@10    |  NDCG@10   |
| :--------- | :--------: | :--------: | :--------: | :--------: |
| Random     |   0.0476   |   0.0277   |   0.0965   |   0.0433   |
| TopPop     | **0.5429** | **0.4153** | **0.6644** | **0.4547** |
| UserKNN CF |   0.3506   |   0.2983   |   0.3922   |   0.3117   |
| ItemKNN CF |   0.3821   |   0.3165   |   0.4372   |   0.3343   |
| P3alpha    |   0.3510   |   0.2989   |   0.3891   |   0.3112   |
| RP3beta    |   0.3511   |   0.2980   |   0.3892   |   0.3103   |
| PureSVD    |   0.3715   |   0.2989   |   0.4473   |   0.3234   |
| CMN        |   0.4195   |   0.3346   |   0.4953   |   0.3592   |


|  Pinterest          |    HR@5    |   NDCG@5   |   HR@10    |  NDCG@10   |
| :--------- | :--------: | :--------: | :--------: | :--------: |
| Random     |   0.0495   |   0.0293   |   0.0982   |   0.0449   |
| TopPop     |   0.1668   |   0.1066   |   0.2745   |   0.1411   |
| UserKNN CF | **0.6886** | **0.4936** |   0.8527   | **0.5470** |
| ItemKNN CF | **0.6966** | **0.4994** | **0.8647** | **0.5542** |
| P3alpha    |   0.6871   | **0.4935** |   0.8449   | **0.5450** |
| RP3beta    | **0.7018** | **0.5041** | **0.8644** | **0.5571** |
| PureSVD    |   0.6440   |   0.4565   |   0.8064   |   0.5095   |
| CMN        |   0.6872   |   0.4883   |   0.8549   |   0.5430   |




| Algorithm | Parameter            | citeulike | pinterest | epinions |
| :-------- | :------------------- | :-------: | :-------: | :------: |
| UserKNN CF          | topK                 |    690    |    769    |   462    |
|           | shrink               |     0     |     0     |   771    |
|           | similarity           |  cosine   |  cosine   |  cosine  |
|           | normalize            |   True    |   True    |   True   |
|           | feature weighting    |   BM25    |  TF-IDF   |  TF-IDF  |
| ItemKNN CF          | topK                 |    713    |    766    |   800    |
|           | shrink               |   1000    |   1000    |    0     |
|           | similarity           |  cosine   |  cosine   |  cosine  |
|           | normalize            |   True    |   True    |  False   |
|           | feature weighting    |  TF-IDF   |   BM25    |  TF-IDF  |
| P3alpha          | topK                 |    743    |    398    |   800    |
|           | alpha                |  0.7226   |  0.7817   |  0.1105  |
|           | normalize similarity |   True    |   True    |  False   |
| RP3beta          | topK                 |    800    |    799    |   800    |
|           | alpha                |  0.7419   |  1.0989   |  0.0237  |
|           | beta                 |  0.1262   |  0.4520   |  0.0000  |
|           | normalize similarity |   True    |   True    |  False   |
| PureSVD          | num factors          |    250    |    66     |    15    |
| CMN          | epochs               |    50     |    15     |    5     |
|           | epochs gmf           |    100    |    100    |   100    |
|           | hops                 |     3     |     3     |    3     |
|           | neg samples          |     4     |     4     |    4     |
|           | reg l2 cmn           | 1.00E-01  | 1.00E-01  | 1.00E-01 |
|           | reg l2 gmf           | 1.00E-04  | 1.00E-04  | 1.00E-04 |
|           | pretrain             |   True    |   True    |   True   |
|           | learning rate        | 1.00E-03  | 1.00E-03  | 1.00E-03 |
|           | verbose              |   False   |   False   |  False   |
|           | batch size           |    128    |    256    |   128    |
|           | embed size           |    50     |    50     |    40    |









### RecSys: Spectral Collaborative Filtering

| amazon instant video           |   REC@20   |   MAP@20   |   REC@40   |   MAP@40   |   REC@60   |   MAP@60   |   REC@80   |   MAP@80   |  REC@100   |  MAP@100   |
| :--------- | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: |
| Random     |   0.0047   |   0.0004   |   0.0079   |   0.0005   |   0.0116   |   0.0006   |   0.0142   |   0.0006   |   0.0185   |   0.0007   |
| TopPop     | **0.1155** | **0.0265** | **0.1737** | **0.0286** | **0.2130** | **0.0295** | **0.2458** | **0.0300** | **0.2758** | **0.0304** |
| UserKNN CF | **0.2397** | **0.0985** | **0.2967** | **0.1008** | **0.3332** | **0.1016** | **0.3555** | **0.1020** | **0.3739** | **0.1022** |
| ItemKNN CF | **0.2359** | **0.0982** | **0.2964** | **0.1006** | **0.3327** | **0.1014** | **0.3559** | **0.1018** | **0.3767** | **0.1021** |
| P3alpha    | **0.2484** | **0.1026** | **0.3059** | **0.1048** | **0.3413** | **0.1056** | **0.3644** | **0.1060** | **0.3808** | **0.1062** |
| RP3beta    | **0.2349** | **0.0930** | **0.2939** | **0.0953** | **0.3340** | **0.0962** | **0.3594** | **0.0966** | **0.3772** | **0.0969** |
| PureSVD    | **0.1179** | **0.0421** | **0.1667** | **0.0440** | **0.1988** | **0.0447** |   0.2250   | **0.0451** |   0.2496   | **0.0454** |
| SpectralCF |   0.0882   |   0.0095   |   0.1497   |   0.0118   |   0.1941   |   0.0128   |   0.2297   |   0.0133   |   0.2568   |   0.0136   |




| Hetrec           |   REC@20   |   MAP@20   |   REC@40   |   MAP@40   |   REC@60   |   MAP@60   |   REC@80   |   MAP@80   |  REC@100   |  MAP@100   |
| :--------- | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: |
| Random     |   0.0019   |   0.0004   |   0.0034   |   0.0004   |   0.0046   |   0.0004   |   0.0058   |   0.0004   |   0.0076   |   0.0005   |
| TopPop     | **0.1811** | **0.0567** | **0.2637** | **0.0608** | **0.3236** | **0.0634** | **0.3764** | **0.0653** | **0.4177** | **0.0665** |
| UserKNN CF | **0.2280** | **0.0897** | **0.3275** | **0.0952** | **0.3873** | **0.0980** | **0.4319** | **0.0999** | **0.4705** | **0.1013** |
| ItemKNN CF | **0.2225** | **0.0854** | **0.3191** | **0.0905** | **0.3834** | **0.0936** | **0.4313** | **0.0956** | **0.4693** | **0.0969** |
| P3alpha    | **0.2292** | **0.0833** | **0.3248** | **0.0886** | **0.3879** | **0.0919** | **0.4305** | **0.0938** | **0.4694** | **0.0952** |
| RP3beta    | **0.2227** | **0.0777** | **0.3217** | **0.0833** | **0.3783** | **0.0862** | **0.4249** | **0.0883** | **0.4608** | **0.0897** |
| PureSVD    | **0.2080** | **0.0780** | **0.2931** | **0.0828** | **0.3551** | **0.0858** | **0.3982** | **0.0877** | **0.4336** | **0.0889** |
| SpectralCF |   0.1597   |   0.0488   |   0.2407   |   0.0527   |   0.2989   |   0.0549   |   0.3467   |   0.0565   |   0.3863   |   0.0576   |




| Movielens Our split           |   REC@20   |   MAP@20   |   REC@40   |   MAP@40   |   REC@60   |   MAP@60   |   REC@80   |   MAP@80   |  REC@100   |  MAP@100   |
| :--------- | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: |
| Random           |   0.0052   |   0.0010   |   0.0109   |   0.0012   |   0.0162   |   0.0013   |   0.0205   |   0.0014   |   0.0255   |   0.0015   |
| TopPop           | **0.1853** | **0.0576** | **0.2710** | **0.0627** | **0.3335** | **0.0659** | **0.3824** | **0.0680** | **0.4244** | **0.0696** |
| UserKNN CF       | **0.2881** | **0.1106** | **0.4026** | **0.1189** | **0.4780** | **0.1238** | **0.5344** | **0.1269** | **0.5790** | **0.1290** |
| ItemKNN CF       | **0.2819** | **0.1059** | **0.3935** | **0.1140** | **0.4712** | **0.1190** | **0.5287** | **0.1221** | **0.5737** | **0.1243** |
| P3alpha          | **0.2853** | **0.1051** | **0.4038** | **0.1142** | **0.4808** | **0.1195** | **0.5352** | **0.1226** | **0.5760** | **0.1248** |
| RP3beta          | **0.2910** | **0.1088** | **0.4072** | **0.1179** | **0.4882** | **0.1233** | **0.5455** | **0.1266** | **0.5884** | **0.1288** |
| PureSVD          | **0.2522** | **0.0918** | **0.3565** | **0.0992** | **0.4318** | **0.1039** | **0.4844** | **0.1068** | **0.5288** | **0.1089** |
| SpectralCF  |   0.1843   |   0.0539   |   0.2661   |   0.0588   |   0.3274   |   0.0618   |   0.3797   |   0.0639   |   0.4254   |   0.0656   |



| Movielens Original split          |   REC@20   |   MAP@20   |   REC@40   |   MAP@40   |   REC@60   |   MAP@60   |   REC@80   |   MAP@80   |  REC@100   |  MAP@100   |
| :--------- | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: |
| Random     |   0.0048   |   0.0009   |   0.0111   |   0.0011   |   0.0159   |   0.0012   |   0.0213   |   0.0013   |   0.0273   |   0.0014   |
| TopPop     |   0.0336   |   0.0054   |   0.0934   |   0.0083   |   0.1209   |   0.0092   |   0.1590   |   0.0102   |   0.2131   |   0.0115   |
| UserKNN CF |   0.0806   |   0.0164   |   0.1392   |   0.0194   |   0.1834   |   0.0210   |   0.2204   |   0.0221   |   0.2503   |   0.0228   |
| ItemKNN CF |   0.0734   |   0.0142   |   0.1250   |   0.0168   |   0.1714   |   0.0185   |   0.2115   |   0.0197   |   0.2459   |   0.0205   |
| P3alpha    |   0.0997   |   0.0191   |   0.1833   |   0.0237   |   0.2465   |   0.0265   |   0.2939   |   0.0282   |   0.3313   |   0.0295   |
| RP3beta    |   0.0896   |   0.0176   |   0.1650   |   0.0216   |   0.2290   |   0.0241   |   0.2774   |   0.0258   |   0.3208   |   0.0272   |
| PureSVD    |   0.0707   |   0.0138   |   0.1220   |   0.0164   |   0.1604   |   0.0178   |   0.1911   |   0.0186   |   0.2207   |   0.0193   |
| SpectralCF | **0.1556** | **0.0657** | **0.2138** | **0.0685** | **0.2726** | **0.0712** | **0.3162** | **0.0728** | **0.3407** | **0.0736** |





| Algorithm | Parameter            | Movielens 1M ours | Movielens 1M original |  hetrec  |  amazon  |
| :-------- | :------------------- | :---------------: | :-------------------: | :------: | :------: |
| UserKNN CF          | topK                 |        341        |          800          |   333    |   213    |
|           | shrink               |         0         |          965          |    0     |    0     |
|           | similarity           |      cosine       |        cosine         |  cosine  |  cosine  |
|           | normalize            |       True        |         False         |   True   |   True   |
|           | feature weighting    |      TF-IDF       |         none          |  TF-IDF  |   none   |
| ItemKNN CF          | topK                 |        289        |          218          |   390    |   466    |
|           | shrink               |        15         |          20           |   862    |   1000   |
|           | similarity           |      cosine       |        cosine         |  cosine  |  cosine  |
|           | normalize            |       True        |         True          |   True   |  False   |
|           | feature weighting    |      TF-IDF       |        TF-IDF         |  TF-IDF  |  TF-IDF  |
| P3alpha          | topK                 |        350        |          371          |   800    |   538    |
|           | alpha                |      0.9104       |        0.8629         |  0.6982  |  0.3676  |
|           | normalize similarity |       True        |         True          |   True   |  False   |
| RP3beta          | topK                 |        203        |          657          |   763    |   561    |
|           | alpha                |      0.6683       |        0.9870         |  0.0000  |  0.3784  |
|           | beta                 |      0.4597       |        0.4301         |  0.0249  |  0.0000  |
|           | normalize similarity |       True        |         True          |   True   |   True   |
| PureSVD           | num factors          |        13         |          10           |    14    |    31    |
| SpectralCF          | epochs               |       865        |          840          |   185    |   220    |
|           | batch size           |       1024        |         1024          |   1024   |   1024   |
|           | embedding size       |        4         |          16           |    16    |    16    |
|           | decay                |      0.0012       |        0.0010         |  0.0010  |  0.0010  |
|           | k                    |         2         |           3           |    3     |    3     |
|           | learning rate        |     1.71E-03      |       1.00E-03        | 1.00E-03 | 1.00E-03 |














### KDD: Leveraging Meta-path based Context for Top-N Recommendation with a NeuralCo-Attention Model



| Movielens 100k              |  PREC@10   |   REC@10   |  NDCG@10   |
| :------------ | :--------: | :--------: | :--------: |
| Random        |   0.0141   |   0.0063   |   0.0077   |
| TopPop        |   0.1907   |   0.1180   |   0.1361   |
| UserKNN CF    |   0.2913   |   0.1802   |   0.2055   |
| ItemKNN CF    | **0.3327** | **0.2199** | **0.2603** |
| P3alpha       |   0.2137   |   0.1585   |   0.1838   |
| RP3beta       |   0.2357   |   0.1684   |   0.1923   |
| PureSVD       |   0.1289   |   0.1087   |   0.1177   |
| ItemKNN CBF   |   0.0294   |   0.0089   |   0.0109   |
| ItemKNN CFCBF | **0.3363** | **0.2103** | **0.2466** |
| MCRec         |   0.3077   |   0.2061   |   0.2363   |




| Algorithm | Parameter            |   *Movielens 100k*    |
| :-------- | :------------------- | :-------------------: |
| UserKNN CF          | topK                 |          128          |
|           | shrink               |           0           |
|           | similarity           |        cosine         |
|           | normalize            |         True          |
|           | feature weighting    |         BM25          |
| ItemKNN CF          | topK                 |          465          |
|           | shrink               |           0           |
|           | similarity           |        cosine         |
|           | normalize            |         True          |
|           | feature weighting    |         BM25          |
| P3alpha          | topK                 |          386          |
|           | alpha                |        1.6651         |
|           | normalize similarity |         False         |
| RP3beta           | topK                 |          711          |
|           | alpha                |        1.4704         |
|           | beta                 |        0.4781         |
|           | normalize similarity |         False         |
| PureSVD          | num factors          |          250          |
| ItemKNN CBF          | topK                 |           5           |
|           | shrink               |           0           |
|           | similarity           |        cosine         |
|           | normalize            |         True          |
|           | feature weighting    |         BM25          |
| ItemKNN CFCBF          | topK                 |          374          |
|           | shrink               |           0           |
|           | similarity           |        cosine         |
|           | normalize            |         False         |
|           | feature weighting    |         BM25          |
|           | ICM weight           |        0.0100         |
| MCRec          | epochs               |          100          |
|           | latent dim           |          128          |
|           | reg latent           |       0.00E+00        |
|           | layers               | \[512, 256, 128, 64\] |
|           | reg layes            |    \[0, 0, 0, 0\]     |
|           | learning rate        |       1.00E-03        |
|           | batch size           |          256          |
|           | num negatives        |           4           |



















### KDD: Collaborative Variational Autoencoder for Recommender Systems


|  Citeulike a 1   |   REC@50   |  REC@100   |  REC@150   |  REC@200   |  REC@250   |  REC@300   |
| :--------------- | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: |
| Random           |   0.0028   |   0.0055   |   0.0085   |   0.0115   |   0.0144   |   0.0175   |
| TopPop           |   0.0231   |   0.0349   |   0.0458   |   0.0520   |   0.0587   |   0.0647   |
| UserKNN CF       |   0.0027   |   0.0053   |   0.0069   |   0.0103   |   0.0127   |   0.0154   |
| ItemKNN CF       |   0.0027   |   0.0053   |   0.0069   |   0.0103   |   0.0127   |   0.0154   |
| P3alpha          |   0.0027   |   0.0053   |   0.0069   |   0.0103   |   0.0127   |   0.0154   |
| RP3beta          |   0.0027   |   0.0053   |   0.0069   |   0.0103   |   0.0127   |   0.0154   |
| PureSVD          |   0.0054   |   0.0103   |   0.0156   |   0.0220   |   0.0295   |   0.0379   |
| ItemKNN CBF      | **0.0697** |   0.0942   |   0.1085   |   0.1180   |   0.1247   |   0.1300   |
| ItemKNN CFCBF    | **0.0729** |   0.1010   |   0.1190   |   0.1322   |   0.1414   |   0.1491   |
| CollaborativeVAE |   0.0666   | **0.1028** | **0.1301** | **0.1531** | **0.1722** | **0.1901** |
|                  |            |            |            |            |            |            |

|  Citeulike a 10  |   REC@50   |  REC@100   |  REC@150   |  REC@200   |  REC@250   |  REC@300   |
| :--------------- | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: |
| Random           |   0.0026   |   0.0054   |   0.0083   |   0.0116   |   0.0143   |   0.0167   |
| TopPop           |   0.0044   |   0.0081   |   0.0103   |   0.0178   |   0.0229   |   0.0258   |
| UserKNN CF       |   0.0683   |   0.1016   |   0.1237   |   0.1407   |   0.1556   |   0.1685   |
| ItemKNN CF       | **0.0788** |   0.1153   |   0.1401   |   0.1577   |   0.1715   |   0.1823   |
| P3alpha          | **0.0788** |   0.1151   |   0.1384   |   0.1555   |   0.1681   |   0.1784   |
| RP3beta          | **0.0811** |   0.1184   |   0.1399   |   0.1565   |   0.1690   |   0.1799   |
| PureSVD          |   0.0515   |   0.0771   |   0.0974   |   0.1132   |   0.1264   |   0.1380   |
| ItemKNN CBF      | **0.1687** | **0.2435** | **0.2930** | **0.3299** | **0.3603** | **0.3878** |
| ItemKNN CFCBF    | **0.1837** | **0.2777** | **0.3382** | **0.3848** | **0.4215** | **0.4486** |
| CollaborativeVAE |   0.0772   |   0.1548   |   0.2188   |   0.2730   |   0.3202   |   0.3602   |






  Citeulike t 1   |   REC@50   |  REC@100   |  REC@150   |  REC@200   |  REC@250   |  REC@300   |
| :--------------- | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: |
| Random           |   0.0019   |   0.0039   |   0.0053   |   0.0076   |   0.0092   |   0.0110   |
| TopPop           |   0.0130   |   0.0192   |   0.0254   |   0.0312   |   0.0382   |   0.0439   |
| UserKNN CF       |   0.0012   |   0.0038   |   0.0065   |   0.0084   |   0.0104   |   0.0123   |
| ItemKNN CF       |   0.0012   |   0.0038   |   0.0065   |   0.0084   |   0.0104   |   0.0123   |
| P3alpha          |   0.0012   |   0.0038   |   0.0065   |   0.0084   |   0.0104   |   0.0123   |
| RP3beta          |   0.0012   |   0.0038   |   0.0065   |   0.0084   |   0.0104   |   0.0123   |
| PureSVD          |   0.0061   |   0.0105   |   0.0155   |   0.0204   |   0.0240   |   0.0267   |
| ItemKNN CBF      | **0.0575** | **0.0685** |   0.0730   |   0.0752   |   0.0769   |   0.0788   |
| ItemKNN CFCBF    | **0.0745** | **0.1027** | **0.1222** | **0.1339** | **0.1412** | **0.1466** |
| CollaborativeVAE |   0.0393   |   0.0600   |   0.0751   |   0.0891   |   0.1011   |   0.1119   |
|                  |            |            |            |            |            |            |

|  Citeulike t 10  |   REC@50   |  REC@100   |  REC@150   |  REC@200   |  REC@250   |  REC@300   |
| :--------------- | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: |
| Random           |   0.0019   |   0.0037   |   0.0055   |   0.0079   |   0.0100   |   0.0121   |
| TopPop           |   0.0576   |   0.0871   |   0.1085   |   0.1253   |   0.1407   |   0.1544   |
| UserKNN CF       |   0.1716   |   0.2131   |   0.2362   |   0.2514   |   0.2624   |   0.2709   |
| ItemKNN CF       |   0.1712   |   0.2132   |   0.2362   |   0.2514   |   0.2623   |   0.2708   |
| P3alpha          |   0.1758   |   0.2183   |   0.2435   |   0.2578   |   0.2672   |   0.2741   |
| RP3beta          |   0.1634   |   0.2112   |   0.2370   |   0.2541   |   0.2647   |   0.2729   |
| PureSVD          |   0.0989   |   0.1314   |   0.1563   |   0.1766   |   0.1954   |   0.2105   |
| ItemKNN CBF      |   0.1198   |   0.1680   |   0.2052   |   0.2362   |   0.2626   |   0.2863   |
| ItemKNN CFCBF    | **0.2311** | **0.2997** |   0.3413   |   0.3754   |   0.3988   |   0.4205   |
| CollaborativeVAE |   0.2149   |   0.2936   | **0.3447** | **0.3856** | **0.4154** | **0.4407** |






| Algorithm | Parameter            | citeulike a 1 | citeulike a 10 | citeulike t 1 | citeulike t 10 |
| :-------- | :------------------- | :-----------: | :------------: | :-----------: | :------------: |
| UserKNN CF          | topK                 |      713      |      645       |      607      |      489       |
|           | shrink               |      108      |       0        |      557      |      554       |
|           | similarity           |    cosine     |     cosine     |    cosine     |     cosine     |
|           | normalize            |     True      |     False      |     False     |      True      |
|           | feature weighting    |     BM25      |      none      |    TF-IDF     |      none      |
| ItemKNN CF           | topK                 |      609      |      576       |      532      |      800       |
|           | shrink               |      112      |      1000      |      386      |      890       |
|           | similarity           |    cosine     |     cosine     |    cosine     |     cosine     |
|           | normalize            |     True      |      True      |     False     |     False      |
|           | feature weighting    |     BM25      |      none      |     BM25      |     TF-IDF     |
| P3alpha           | topK                 |      512      |      200       |      421      |      566       |
|           | alpha                |    0.8382     |     0.3731     |    1.7685     |     0.0388     |
|           | normalize similarity |     True      |     False      |     True      |     False      |
| RP3beta          | topK                 |      247      |      397       |      283      |      601       |
|           | alpha                |    0.8076     |     0.6850     |    1.3923     |     0.0000     |
|           | beta                 |    1.1783     |     0.0000     |    0.1345     |     0.0000     |
|           | normalize similarity |     False     |     False      |     False     |      True      |
| PureSVD          | num factors          |      250      |      250       |      250      |      250       |
| ItemKNN CBF          | topK                 |      196      |      656       |      50       |      640       |
|           | shrink               |      199      |       4        |      131      |       1        |
|           | similarity           |    cosine     |     cosine     |    cosine     |     cosine     |
|           | normalize            |     False     |      True      |     True      |      True      |
| ItemKNN CFCBF          | topK                 |      281      |      676       |      198      |      800       |
|           | shrink               |      999      |      1000      |      77       |       0        |
|           | similarity           |    cosine     |     cosine     |    cosine     |     cosine     |
|           | normalize            |     True      |     False      |     False     |     False      |
|           | feature weighting    |     none      |      BM25      |    TF-IDF     |     TF-IDF     |
|           | ICM weight           |    7.9294     |     1.2653     |    0.3588     |     1.5805     |
| CollaborativeVAE           | epochs               |      10       |       35       |      10       |       25       |
|           | learning rate vae    |   1.00E-02    |    1.00E-02    |   1.00E-02    |    1.00E-02    |
|           | learning rate cvae   |   1.00E-03    |    1.00E-03    |   1.00E-03    |    1.00E-03    |
|           | num factors          |      50       |       50       |      50       |       50       |
|           | dimensions vae       | \[200, 100\]  |  \[200, 100\]  | \[200, 100\]  |  \[200, 100\]  |
|           | epochs vae           |  \[50, 50\]   |   \[50, 50\]   |  \[50, 50\]   |   \[50, 50\]   |
|           | batch size           |      128      |      128       |      128      |      128       |
|           | lambda u             |   1.00E-01    |    1.00E-01    |   1.00E-01    |    1.00E-01    |
|           | lambda v             |   1.00E+01    |    1.00E+01    |   1.00E+01    |    1.00E+01    |
|           | lambda r             |   1.00E+00    |    1.00E+00    |   1.00E+00    |    1.00E+00    |
|           | a                    |       1       |       1        |       1       |       1        |
|           | b                    |    0.0100     |     0.0100     |    0.0100     |     0.0100     |
|           | M                    |      300      |      300       |      300      |      300       |












### KDD: Collaborative Deep Learning

|  Citeulike a 1   |   REC@50   |  REC@100   |  REC@150   |  REC@200   |  REC@250   |  REC@300   |
| :--------------- | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: |
| Random          |   0.0028   |   0.0057   |   0.0085   |   0.0113   |   0.0144   |   0.0173   |
| TopPop          |   0.0227   |   0.0348   |   0.0425   |   0.0483   |   0.0546   |   0.0607   |
| UserKNN CF      |   0.0027   |   0.0053   |   0.0069   |   0.0102   |   0.0127   |   0.0154   |
| ItemKNN CF      |   0.0027   |   0.0053   |   0.0069   |   0.0102   |   0.0127   |   0.0154   |
| P3alpha         |   0.0027   |   0.0053   |   0.0069   |   0.0102   |   0.0127   |   0.0154   |
| RP3beta         |   0.0027   |   0.0053   |   0.0069   |   0.0102   |   0.0127   |   0.0154   |
| PureSVD         |   0.0057   |   0.0113   |   0.0168   |   0.0233   |   0.0303   |   0.0381   |
| ItemKNN CBF     | **0.0942** |   0.1336   |   0.1616   |   0.1825   |   0.2000   |   0.2152   |
| ItemKNN CFCBF   |   0.0707   |   0.1015   |   0.1224   |   0.1373   |   0.1495   |   0.1597   |
| CollaborativeDL |   0.0915   | **0.1387** | **0.1733** | **0.2023** | **0.2265** | **0.2477** |
|                  |            |            |            |            |            |            |

|  Citeulike a 10  |   REC@50   |  REC@100   |  REC@150   |  REC@200   |  REC@250   |  REC@300   |
| :--------------- | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: |
| Random          |   0.0028   |   0.0058   |   0.0089   |   0.0116   |   0.0149   |   0.0182   |
| TopPop          |   0.0038   |   0.0073   |   0.0120   |   0.0167   |   0.0232   |   0.0258   |
| UserKNN CF      | **0.0685** |   0.1028   |   0.1271   |   0.1453   |   0.1597   |   0.1710   |
| ItemKNN CF      | **0.0846** | **0.1213** |   0.1459   |   0.1646   |   0.1766   |   0.1861   |
| P3alpha         | **0.0718** | **0.1079** |   0.1331   |   0.1513   |   0.1656   |   0.1777   |
| RP3beta         | **0.0800** | **0.1167** |   0.1406   |   0.1576   |   0.1706   |   0.1815   |
| PureSVD         |   0.0510   |   0.0774   |   0.0968   |   0.1124   |   0.1250   |   0.1369   |
| ItemKNN CBF     | **0.2135** | **0.3038** | **0.3625** | **0.4070** | **0.4412** | **0.4707** |
| ItemKNN CFCBF   | **0.1945** | **0.2896** | **0.3493** | **0.3965** | **0.4322** | **0.4620** |
| CollaborativeDL |   0.0543   |   0.1035   |   0.1479   |   0.1907   |   0.2276   |   0.2627   |






  Citeulike t 1   |   REC@50   |  REC@100   |  REC@150   |  REC@200   |  REC@250   |  REC@300   |
| :--------------- | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: |
| Random          |   0.0021   |   0.0042   |   0.0061   |   0.0082   |   0.0100   |   0.0114   |
| TopPop          |   0.0130   |   0.0180   |   0.0337   |   0.0374   |   0.0453   |   0.0502   |
| UserKNN CF      |   0.0012   |   0.0038   |   0.0065   |   0.0084   |   0.0104   |   0.0123   |
| ItemKNN CF      |   0.0012   |   0.0038   |   0.0065   |   0.0084   |   0.0104   |   0.0123   |
| P3alpha         |   0.0012   |   0.0038   |   0.0065   |   0.0084   |   0.0104   |   0.0123   |
| RP3beta         |   0.0012   |   0.0038   |   0.0065   |   0.0084   |   0.0104   |   0.0123   |
| PureSVD         |   0.0055   |   0.0101   |   0.0163   |   0.0218   |   0.0250   |   0.0277   |
| ItemKNN CBF     |   0.0479   |   0.0559   |   0.0589   |   0.0609   |   0.0625   |   0.0644   |
| ItemKNN CFCBF   | **0.0731** | **0.1026** | **0.1236** | **0.1383** |   0.1492   |   0.1579   |
| CollaborativeDL |   0.0487   |   0.0859   |   0.1117   |   0.1328   | **0.1497** | **0.1661** |
|                  |            |            |            |            |            |            |

|  Citeulike t 10  |   REC@50   |  REC@100   |  REC@150   |  REC@200   |  REC@250   |  REC@300   |
| :--------------- | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: |
| Random          |   0.0024   |   0.0036   |   0.0051   |   0.0073   |   0.0095   |   0.0113   |
| TopPop          |   0.0578   |   0.0869   |   0.1082   |   0.1256   |   0.1409   |   0.1544   |
| UserKNN CF      |   0.1704   |   0.2146   |   0.2364   |   0.2509   |   0.2610   |   0.2698   |
| ItemKNN CF      |   0.1704   |   0.2142   |   0.2364   |   0.2508   |   0.2611   |   0.2699   |
| P3alpha         |   0.1769   |   0.2208   |   0.2443   |   0.2594   |   0.2679   |   0.2743   |
| RP3beta         |   0.1675   |   0.2126   |   0.2384   |   0.2555   |   0.2664   |   0.2735   |
| PureSVD         |   0.0993   |   0.1344   |   0.1573   |   0.1780   |   0.1952   |   0.2103   |
| ItemKNN CBF     |   0.1510   |   0.2086   |   0.2476   |   0.2774   |   0.3086   |   0.3302   |
| ItemKNN CFCBF   | **0.2139** |   0.2816   |   0.3249   |   0.3595   |   0.3860   |   0.4079   |
| CollaborativeDL |   0.2068   | **0.2837** | **0.3354** | **0.3761** | **0.4116** | **0.4397** |






| Algorithm | Parameter            | citeulike a 1 | citeulike a 10 | citeulike t 1 | citeulike t 10 |
| :-------- | :------------------- | :-----------: | :------------: | :-----------: | :------------: |
| UserKNN CF          | topK                 |      187      |      276       |      679      |      793       |
|           | shrink               |      845      |      1000      |      382      |      951       |
|           | similarity           |    cosine     |     cosine     |    cosine     |     cosine     |
|           | normalize            |     False     |      True      |     False     |      True      |
|           | feature weighting    |     none      |     TF-IDF     |     none      |      none      |
| ItemKNN CF          | topK                 |      269      |      800       |      575      |      800       |
|           | shrink               |      242      |      1000      |      750      |       0        |
|           | similarity           |    cosine     |     cosine     |    cosine     |     cosine     |
|           | normalize            |     False     |      True      |     True      |     False      |
|           | feature weighting    |     none      |     TF-IDF     |    TF-IDF     |     TF-IDF     |
| P3alpha          | topK                 |      627      |      800       |      637      |      389       |
|           | alpha                |    1.9088     |     0.0746     |    1.0359     |     0.0033     |
|           | normalize similarity |     False     |     False      |     True      |     False      |
| RP3beta          | topK                 |      659      |      448       |      430      |      800       |
|           | alpha                |    1.7581     |     0.7017     |    1.2094     |     0.4068     |
|           | beta                 |    1.0041     |     0.0000     |    0.7875     |     0.0000     |
|           | normalize similarity |     False     |     False      |     True      |      True      |
| PureSVD          | num factors          |      250      |      237       |      250      |      233       |
| ItemKNN CBF          | topK                 |      673      |      800       |      36       |      800       |
|           | shrink               |      827      |      1000      |      74       |       16       |
|           | similarity           |    cosine     |     cosine     |    cosine     |     cosine     |
|           | normalize            |     True      |      True      |     False     |      True      |
|           | feature weighting    |     BM25      |      BM25      |     none      |     TF-IDF     |
| ItemKNN CFCBF          | topK                 |      476      |      800       |      345      |      800       |
|           | shrink               |      657      |      1000      |      515      |      1000      |
|           | similarity           |    cosine     |     cosine     |    cosine     |     cosine     |
|           | normalize            |     False     |     False      |     True      |     False      |
|           | feature weighting    |     none      |      BM25      |    TF-IDF     |      BM25      |
|           | ICM weight           |    0.0951     |     1.5144     |    0.0885     |     7.3378     |
| CollaborativeDL          | para lv              |      10       |       10       |      10       |       10       |
|           | para lu              |       1       |       1        |       1       |       1        |
|           | para ln              |   1000.0000   |   1000.0000    |   1000.0000   |   1000.0000    |
|           | batch size           |      128      |      128       |      128      |      128       |
|           | epoch sdae           |      200      |      200       |      200      |      200       |
|           | epoch dae            |      200      |      200       |      200      |      200       |



















### WWW: Neural Collaborative Filtering





| Movielens 1M           |    HR@1    |   NDCG@1   |    HR@5    |   NDCG@5   |   HR@10    |  NDCG@10   |
| :--------- | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: |
| Random     |   0.0084   |   0.0084   |   0.0510   |   0.0290   |   0.0987   |   0.0442   |
| TopPop     |   0.1051   |   0.1051   |   0.3043   |   0.2062   |   0.4531   |   0.2542   |
| UserKNN CF |   0.1666   |   0.1666   |   0.4916   |   0.3328   |   0.6705   |   0.3908   |
| ItemKNN CF |   0.1758   |   0.1758   |   0.4829   |   0.3328   |   0.6596   |   0.3900   |
| P3alpha    |   0.1760   |   0.1760   |   0.4811   |   0.3331   |   0.6464   |   0.3867   |
| RP3beta    |   0.1821   |   0.1821   |   0.4922   |   0.3409   |   0.6715   |   0.3991   |
| PureSVD    | **0.2123** | **0.2123** | **0.5377** | **0.3802** | **0.6896** | **0.4294** |
| NeuMF      |   0.1841   |   0.1841   |   0.4980   |   0.3445   |   0.6725   |   0.4011   |


|  Pinterest          |    HR@1    |   NDCG@1   |    HR@5    |   NDCG@5   |   HR@10    |  NDCG@10   |
| :--------- | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: |
| Random     |   0.0100   |   0.0100   |   0.0490   |   0.0290   |   0.0978   |   0.0446   |
| TopPop     |   0.0470   |   0.0470   |   0.1663   |   0.1065   |   0.2744   |   0.1412   |
| UserKNN CF | **0.2887** | **0.2887** | **0.7001** | **0.5033** |   0.8610   | **0.5557** |
| ItemKNN CF | **0.2917** | **0.2917** | **0.7100** | **0.5092** | **0.8744** | **0.5629** |
| P3alpha    | **0.2852** | **0.2852** | **0.7008** | **0.5018** | **0.8667** | **0.5559** |
| RP3beta    | **0.2950** | **0.2950** | **0.7105** | **0.5116** | **0.8740** | **0.5650** |
| PureSVD    |   0.2586   |   0.2586   |   0.6576   |   0.4654   |   0.8216   |   0.5188   |
| NeuMF      |   0.2690   |   0.2690   |   0.6915   |   0.4879   |   0.8657   |   0.5447   |




| Algorithm | Parameter            |   Movielens 1M    |     Pinterest     |
| :-------- | :------------------- | :---------------: | :---------------: |
| UserKNN CF          | topK                 |        800        |        800        |
|           | shrink               |         0         |         0         |
|           | similarity           |      cosine       |      cosine       |
|           | normalize            |       True        |       True        |
|           | feature weighting    |       BM25        |      TF-IDF       |
| ItemKNN CF          | topK                 |        288        |        776        |
|           | shrink               |       1000        |         0         |
|           | similarity           |      cosine       |      cosine       |
|           | normalize            |       True        |       True        |
|           | feature weighting    |       BM25        |      TF-IDF       |
| P3alpha          | topK                 |        464        |        800        |
|           | alpha                |      1.5511       |      2.0000       |
|           | normalize similarity |       True        |       True        |
| RP3beta          | topK                 |        494        |        800        |
|           | alpha                |      1.1468       |      0.0000       |
|           | beta                 |      0.5613       |      0.5394       |
|           | normalize similarity |       True        |       True        |
| PureSVD          | num factors          |        60         |        48         |
| NeuMF          | epochs               |        35         |         5         |
|           | epochs gmf           |        70         |        100        |
|           | epochs mlp           |        70         |        15         |
|           | batch size           |        256        |        256        |
|           | num factors          |         8         |         8         |
|           | layers               | \[64, 32, 16, 8\] | \[64, 32, 16, 8\] |
|           | reg mf               |     0.00E+00      |     0.00E+00      |
|           | reg layers           |  \[0, 0, 0, 0\]   |  \[0, 0, 0, 0\]   |
|           | num negatives        |         4         |         4         |
|           | learning rate        |     1.00E-03      |     1.00E-03      |
|           | learner              |       adam        |       adam        |
|           | pretrain             |       True        |       True        |


































### WWW: Variational Autoencoders for Collaborative Filtering


| Movielens 20M  |   REC@20   |  NDCG@20   |   REC@50   |  NDCG@50   |  REC@100   |  NDCG@100  |
| :------------- | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: |
| Random         |   0.0011   |   0.0009   |   0.0027   |   0.0016   |   0.0050   |   0.0024   |
| TopPop         |   0.1441   |   0.1201   |   0.2320   |   0.1569   |   0.3296   |   0.1901   |
| ItemKNN CF     |   0.2851   |   0.2428   |   0.4328   |   0.3030   |   0.5547   |   0.3459   |
| P3alpha        |   0.2607   |   0.2157   |   0.4053   |   0.2739   |   0.5296   |   0.3179   |
| RP3beta        |   0.2949   |   0.2454   |   0.4411   |   0.3054   |   0.5694   |   0.3507   |
| SLIMElasticNet |   0.3349   |   0.2915   |   0.4893   |   0.3572   |   0.6103   |   0.4012   |
| Mult-VAE       | **0.3540** | **0.2993** | **0.5220** | **0.3693** | **0.6488** | **0.4154** |


|  Netflix Prize |   REC@20   |  NDCG@20   |   REC@50   |  NDCG@50   |  REC@100   |  NDCG@100  |
| :------------- | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: |
| Random         |   0.0011   |   0.0011   |   0.0031   |   0.0020   |   0.0058   |   0.0031   |
| TopPop         |   0.0782   |   0.0761   |   0.1643   |   0.1159   |   0.2718   |   0.1570   |
| ItemKNN CF     |   0.2088   |   0.1966   |   0.3386   |   0.2588   |   0.4590   |   0.3086   |
| P3alpha        |   0.1977   |   0.1762   |   0.3346   |   0.2414   |   0.4675   |   0.2967   |
| RP3beta        |   0.2196   |   0.2044   |   0.3560   |   0.2699   |   0.4886   |   0.3246   |
| SLIMElasticNet |   0.2551   | **0.2473** |   0.3995   | **0.3196** |   0.5289   |   0.3745   |
| Mult-VAE       | **0.2626** |   0.2448   | **0.4138** |   0.3192   | **0.5476** | **0.3756** |




| Algorithm | Parameter            | movielens20m | netflixPrize |
| :-------- | :------------------- | :----------: | :----------: |
| ItemKNN CF          | topK                 |     312      |     160      |
|           | shrink               |      10      |     965      |
|           | similarity           |    cosine    |    cosine    |
|           | normalize            |     True     |     True     |
|           | feature weighting    |    TF-IDF    |     BM25     |
| P3alpha          | topK                 |     533      |     684      |
|           | alpha                |    0.4313    |    2.0000    |
|           | normalize similarity |     True     |     True     |
| RP3beta          | topK                 |     348      |     290      |
|           | alpha                |    1.2252    |    0.8838    |
|           | beta                 |    0.3832    |    0.5335    |
|           | normalize similarity |     True     |     True     |
| SLIMElasticNet          | topK                 |     800      |     800      |
|           | l1 ratio             |   1.45E-02   |   1.00E-05   |
|           | alpha                |    0.0010    |    0.0010    |
| Mult-VAE          | epochs               |      65      |      60      |
|           | batch size           |     500      |     500      |
|           | total anneal steps   |    200000    |    200000    |
|           | p dims               |      \-      |      \-      |

