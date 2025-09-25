# Challenge Description
When looking for changes between similar files, eyeballing them might not be the most efficient approach! This is where the diff command becomes invaluable.

diff compares two files line by line and shows you exactly what's different between them. For example:
```bash
hacker@dojo:~$ cat file1
hello
world
hacker@dojo:~$ cat file2
hello
universe
hacker@dojo:~$ diff file1 file2
2c2
< world
---
> universe
```
The output tells us that line 2 changed (2c2), with world in the first file (<) being replaced by universe in the second file (>).

Sometimes, when new lines are added, you'll see something like:
```bash
hacker@dojo:~$ cat old
pwn
hacker@dojo:~$ cat new
pwn
college
hacker@dojo:~$ diff old new
1a2
> college
```
This tells us that after line 1 in the first file, the second file has an additional line (1a2 means "after line 1 of file1, add line 2 of file2").

Now for your challenge! There are two files in /challenge:

/challenge/decoys_only.txt contains 100 fake flags
/challenge/decoys_and_real.txt contains all 100 fake flags plus the one real flag
Use diff to find what's different between these files and get your flag!
# Thought Process & Solution
Catted both the files to see how the fake flags are stored and then executed the diff cmd to see which is the odd entry. Although since the both files are small so its easy to see the odd one out aka my real flag.
```bash
hacker@commands~comparing-files:~$ cat /challenge/decoys_only.txt
pwn.college{fake_flag_number_1_wRAqLT9bu58}
pwn.college{fake_flag_number_2_wPWutkYKqEE}
pwn.college{fake_flag_number_3_I78cKT0fpKM}
pwn.college{fake_flag_number_4_pRW4q6lXFFA}
pwn.college{fake_flag_number_5_Aey0Q5VkPC0}
pwn.college{fake_flag_number_6_DpZjXDIHc44}
pwn.college{fake_flag_number_7_eiqhAaj7tGk}
pwn.college{fake_flag_number_8_bsAWI49A0P4}
pwn.college{fake_flag_number_9_WDQUnl8HdGI}
pwn.college{fake_flag_number_10_cGI1Tkt2gJs}
pwn.college{fake_flag_number_11_mgVu4NQxCXk}
pwn.college{fake_flag_number_12_d8QFP4G3QK0}
pwn.college{fake_flag_number_13_geMVNq9Xq2g}
pwn.college{fake_flag_number_14_CQ6XlvPXIU8}
pwn.college{fake_flag_number_15_3gsFPIL8CMY}
pwn.college{fake_flag_number_16_Qh7yt6T1AJU}
pwn.college{fake_flag_number_17_0DuQDLpwPM}
pwn.college{fake_flag_number_18_SJRKOV3KAN0}
pwn.college{fake_flag_number_19_UZ5AyG5VcIs}
pwn.college{fake_flag_number_20_3RU7uL30x8}
pwn.college{fake_flag_number_21_RNTTpNwmxDo}
pwn.college{fake_flag_number_22_wbSJ8lqBSWU}
pwn.college{fake_flag_number_23_MoRJxBj1OHs}
pwn.college{fake_flag_number_24_V0kytm1UgM}
pwn.college{fake_flag_number_25_wBWe0IbmcHY}
pwn.college{fake_flag_number_26_yGxQbtTNoVY}
pwn.college{fake_flag_number_27_8azWT7bkc8}
pwn.college{fake_flag_number_28_n5SxDlepllg}
pwn.college{fake_flag_number_29_Y6aMs3yfegY}
pwn.college{fake_flag_number_30_1GKVmVCFpk}
pwn.college{fake_flag_number_31_4qfUP9j0uA}
pwn.college{fake_flag_number_32_zq5E83gumgE}
pwn.college{fake_flag_number_33_ZGt0ejmhbc}
pwn.college{fake_flag_number_34_F2fZdIdlG4}
pwn.college{fake_flag_number_35_9tBS2fKKZ0}
pwn.college{fake_flag_number_36_e3nOLqS8uM}
pwn.college{fake_flag_number_37_SWGoC6PeG8}
pwn.college{fake_flag_number_38_5zsXQsCMtM}
pwn.college{fake_flag_number_39_UTv5otaR3U}
pwn.college{fake_flag_number_40_qzoHnJGLZcs}
pwn.college{fake_flag_number_41_HQTO6S6gtA}
pwn.college{fake_flag_number_42_XJB09IHnE}
pwn.college{fake_flag_number_43_l9lp1nITHAs}
pwn.college{fake_flag_number_44_NXcdrvQIEw}
pwn.college{fake_flag_number_45_wklIAOOcSCo}
pwn.college{fake_flag_number_46_w2FLy1zFCuA}
pwn.college{fake_flag_number_47_iEaQdDbthg}
pwn.college{fake_flag_number_48_yQSLGsW47gU}
pwn.college{fake_flag_number_49_tUAXwuexnM}
pwn.college{fake_flag_number_50_RV20WdgY9AE}
pwn.college{fake_flag_number_51_StsMx6R5NdM}
pwn.college{fake_flag_number_52_vS8hoFCkCKU}
pwn.college{fake_flag_number_53_jWtLrKfTi7o}
pwn.college{fake_flag_number_54_RH17WFfbyw}
pwn.college{fake_flag_number_55_19Lt2YdG8Q}
pwn.college{fake_flag_number_56_aSL1lWlm8Hg}
pwn.college{fake_flag_number_57_QlJXLMah5g8}
pwn.college{fake_flag_number_58_fDL0KJNUYao}
pwn.college{fake_flag_number_59_5idZqMCfg}
pwn.college{fake_flag_number_60_7BFmaWebJFE}
pwn.college{fake_flag_number_61_9LW52UTDjq0}
pwn.college{fake_flag_number_62_nsCDHDiFrrc}
pwn.college{fake_flag_number_63_FWl3FHVAfKk}
pwn.college{fake_flag_number_64_cDFlaDtctQQ}
pwn.college{fake_flag_number_65_KG4liybB0ik}
pwn.college{fake_flag_number_66_ZJmIbgFnaZE}
pwn.college{fake_flag_number_67_X5HtmiOky0A}
pwn.college{fake_flag_number_68_XsPxLXyiS0}
pwn.college{fake_flag_number_69_cNFfrwqNCj8}
pwn.college{fake_flag_number_70_Ikz7xgb493A}
pwn.college{fake_flag_number_71_auz7E5BLR7k}
pwn.college{fake_flag_number_72_EZh4zCiGFw}
pwn.college{fake_flag_number_73_CD4NH98R0qY}
pwn.college{fake_flag_number_74_K0flLCOCAak}
pwn.college{fake_flag_number_75_BSNy5W1HQvs}
pwn.college{fake_flag_number_76_PwHNdqR7X84}
pwn.college{fake_flag_number_77_3oFHQwHYHfc}
pwn.college{fake_flag_number_78_2m6x0pMohfc}
pwn.college{fake_flag_number_79_IuS6vZOmQcI}
pwn.college{fake_flag_number_80_V5qqEwOqn0}
pwn.college{fake_flag_number_81_gfKTTbbkArQ}
pwn.college{fake_flag_number_82_oJAkJy30zFE}
pwn.college{fake_flag_number_83_OToSZVMVxdA}
pwn.college{fake_flag_number_84_DWaIbp2MMU8}
pwn.college{fake_flag_number_85_kffuV05giG4}
pwn.college{fake_flag_number_86_Tz8Kbtn3ik}
pwn.college{fake_flag_number_87_0OiFfAM4aQE}
pwn.college{fake_flag_number_88_yfwuu78uOkM}
pwn.college{fake_flag_number_89_Cc7FG46gncE}
pwn.college{fake_flag_number_90_3GpKLyYa0gc}
pwn.college{fake_flag_number_91_C4q23hsKAIA}
pwn.college{fake_flag_number_92_9oDC2V0zTt0}
pwn.college{fake_flag_number_93_2vVYRHr0PWU}
pwn.college{fake_flag_number_94_G9eUGyom1Rk}
pwn.college{fake_flag_number_95_YasZihhp4M}
pwn.college{fake_flag_number_96_dCRw1UiAy4o}
pwn.college{fake_flag_number_97_0tqhwCQ6dHQ}
pwn.college{fake_flag_number_98_1Te6sAb1zo}
pwn.college{fake_flag_number_99_hxtBuZlFuxk}
pwn.college{fake_flag_number_100_a98pGUrwdqM}
hacker@commands~comparing-files:~$ cat /challenge/decoys_and_real.txt
pwn.college{fake_flag_number_1_wRAqLT9bu58}
pwn.college{fake_flag_number_2_wPWutkYKqEE}
pwn.college{fake_flag_number_3_I78cKT0fpKM}
pwn.college{fake_flag_number_4_pRW4q6lXFFA}
pwn.college{fake_flag_number_5_Aey0Q5VkPC0}
pwn.college{fake_flag_number_6_DpZjXDIHc44}
pwn.college{fake_flag_number_7_eiqhAaj7tGk}
pwn.college{fake_flag_number_8_bsAWI49A0P4}
pwn.college{fake_flag_number_9_WDQUnl8HdGI}
pwn.college{fake_flag_number_10_cGI1Tkt2gJs}
pwn.college{fake_flag_number_11_mgVu4NQxCXk}
pwn.college{fake_flag_number_12_d8QFP4G3QK0}
pwn.college{fake_flag_number_13_geMVNq9Xq2g}
pwn.college{fake_flag_number_14_CQ6XlvPXIU8}
pwn.college{fake_flag_number_15_3gsFPIL8CMY}
pwn.college{fake_flag_number_16_Qh7yt6T1AJU}
pwn.college{fake_flag_number_17_0DuQDLpwPM}
pwn.college{fake_flag_number_18_SJRKOV3KAN0}
pwn.college{fake_flag_number_19_UZ5AyG5VcIs}
pwn.college{fake_flag_number_20_3RU7uL30x8}
pwn.college{fake_flag_number_21_RNTTpNwmxDo}
pwn.college{fake_flag_number_22_wbSJ8lqBSWU}
pwn.college{U6p5kYwgJfYOwgz5Fa8YW-CYDdf.QXzAzM4EDL5EzN0czW}
pwn.college{fake_flag_number_23_MoRJxBj1OHs}
pwn.college{fake_flag_number_24_V0kytm1UgM}
pwn.college{fake_flag_number_25_wBWe0IbmcHY}
pwn.college{fake_flag_number_26_yGxQbtTNoVY}
pwn.college{fake_flag_number_27_8azWT7bkc8}
pwn.college{fake_flag_number_28_n5SxDlepllg}
pwn.college{fake_flag_number_29_Y6aMs3yfegY}
pwn.college{fake_flag_number_30_1GKVmVCFpk}
pwn.college{fake_flag_number_31_4qfUP9j0uA}
pwn.college{fake_flag_number_32_zq5E83gumgE}
pwn.college{fake_flag_number_33_ZGt0ejmhbc}
pwn.college{fake_flag_number_34_F2fZdIdlG4}
pwn.college{fake_flag_number_35_9tBS2fKKZ0}
pwn.college{fake_flag_number_36_e3nOLqS8uM}
pwn.college{fake_flag_number_37_SWGoC6PeG8}
pwn.college{fake_flag_number_38_5zsXQsCMtM}
pwn.college{fake_flag_number_39_UTv5otaR3U}
pwn.college{fake_flag_number_40_qzoHnJGLZcs}
pwn.college{fake_flag_number_41_HQTO6S6gtA}
pwn.college{fake_flag_number_42_XJB09IHnE}
pwn.college{fake_flag_number_43_l9lp1nITHAs}
pwn.college{fake_flag_number_44_NXcdrvQIEw}
pwn.college{fake_flag_number_45_wklIAOOcSCo}
pwn.college{fake_flag_number_46_w2FLy1zFCuA}
pwn.college{fake_flag_number_47_iEaQdDbthg}
pwn.college{fake_flag_number_48_yQSLGsW47gU}
pwn.college{fake_flag_number_49_tUAXwuexnM}
pwn.college{fake_flag_number_50_RV20WdgY9AE}
pwn.college{fake_flag_number_51_StsMx6R5NdM}
pwn.college{fake_flag_number_52_vS8hoFCkCKU}
pwn.college{fake_flag_number_53_jWtLrKfTi7o}
pwn.college{fake_flag_number_54_RH17WFfbyw}
pwn.college{fake_flag_number_55_19Lt2YdG8Q}
pwn.college{fake_flag_number_56_aSL1lWlm8Hg}
pwn.college{fake_flag_number_57_QlJXLMah5g8}
pwn.college{fake_flag_number_58_fDL0KJNUYao}
pwn.college{fake_flag_number_59_5idZqMCfg}
pwn.college{fake_flag_number_60_7BFmaWebJFE}
pwn.college{fake_flag_number_61_9LW52UTDjq0}
pwn.college{fake_flag_number_62_nsCDHDiFrrc}
pwn.college{fake_flag_number_63_FWl3FHVAfKk}
pwn.college{fake_flag_number_64_cDFlaDtctQQ}
pwn.college{fake_flag_number_65_KG4liybB0ik}
pwn.college{fake_flag_number_66_ZJmIbgFnaZE}
pwn.college{fake_flag_number_67_X5HtmiOky0A}
pwn.college{fake_flag_number_68_XsPxLXyiS0}
pwn.college{fake_flag_number_69_cNFfrwqNCj8}
pwn.college{fake_flag_number_70_Ikz7xgb493A}
pwn.college{fake_flag_number_71_auz7E5BLR7k}
pwn.college{fake_flag_number_72_EZh4zCiGFw}
pwn.college{fake_flag_number_73_CD4NH98R0qY}
pwn.college{fake_flag_number_74_K0flLCOCAak}
pwn.college{fake_flag_number_75_BSNy5W1HQvs}
pwn.college{fake_flag_number_76_PwHNdqR7X84}
pwn.college{fake_flag_number_77_3oFHQwHYHfc}
pwn.college{fake_flag_number_78_2m6x0pMohfc}
pwn.college{fake_flag_number_79_IuS6vZOmQcI}
pwn.college{fake_flag_number_80_V5qqEwOqn0}
pwn.college{fake_flag_number_81_gfKTTbbkArQ}
pwn.college{fake_flag_number_82_oJAkJy30zFE}
pwn.college{fake_flag_number_83_OToSZVMVxdA}
pwn.college{fake_flag_number_84_DWaIbp2MMU8}
pwn.college{fake_flag_number_85_kffuV05giG4}
pwn.college{fake_flag_number_86_Tz8Kbtn3ik}
pwn.college{fake_flag_number_87_0OiFfAM4aQE}
pwn.college{fake_flag_number_88_yfwuu78uOkM}
pwn.college{fake_flag_number_89_Cc7FG46gncE}
pwn.college{fake_flag_number_90_3GpKLyYa0gc}
pwn.college{fake_flag_number_91_C4q23hsKAIA}
pwn.college{fake_flag_number_92_9oDC2V0zTt0}
pwn.college{fake_flag_number_93_2vVYRHr0PWU}
pwn.college{fake_flag_number_94_G9eUGyom1Rk}
pwn.college{fake_flag_number_95_YasZihhp4M}
pwn.college{fake_flag_number_96_dCRw1UiAy4o}
pwn.college{fake_flag_number_97_0tqhwCQ6dHQ}
pwn.college{fake_flag_number_98_1Te6sAb1zo}
pwn.college{fake_flag_number_99_hxtBuZlFuxk}
pwn.college{fake_flag_number_100_a98pGUrwdqM}
hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
22a23
> pwn.college{U6p5kYwgJfYOwgz5Fa8YW-CYDdf.QXzAzM4EDL5EzN0czW}
```
**Flag:** `pwn.college{U6p5kYwgJfYOwgz5Fa8YW-CYDdf.QXzAzM4EDL5EzN0czW}`
## New Learning
diff cmd - basically compares two files and its output is the difference of contents in both the files
## Reference
