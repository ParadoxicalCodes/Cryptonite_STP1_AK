# Challenge Description
Sometimes, misbehaving processes can interfere with your work. These processes might need to be killed...

In this challenge, there's a decoy process that's hogging a critical resource - a named pipe (FIFO) at /tmp/flag_fifo into which (like in the Practicing Piping FIFO challenge) /challenge/run wants to write your flag. You need to kill this process.

Your general workflow should be:

  1. Check what processes are running.
  2. Find /challenge/decoy in the list and figure out its process ID.
  3. kill it.
  4. Run /challenge/run to get the flag without being overwhelmed by decoys (you don't need to redirect its output; it'll write to the FIFO on its own).
Good luck!

NOTE: You might see a few decoy flags show up even after killing the decoy process. This happens because Linux pipes are buffered: conceptually, they have a sort of length through which data flows, and you might kill the decoy process while data is in the pipe. That data, having already entered the pipe, will proceed to the other end (your cat). If you wait a second, you'll see the decoys stop, and then you can /challenge/run and win!
# Thought Process & Solution
For some reason my flag is stuck, followed all steps as given but it seems to be buffering. In case it needed to complete the pipe i opened another terminal and catted the tmp file but it also seems to be buffering with decoy flags as output.
> Terminal 1
```bash
hacker@processes~killing-misbehaving-processes:~$ ps auxww | grep /challenge/decoy
root         139  0.0  0.0   5204  3520 ?        S    12:23   0:00 su -c exec /challenge/decoy > /tmp/flag_fifo hacker
hacker       142  0.7  0.0  13516  9280 ?        Ss   12:23   0:00 /usr/bin/python /challenge/decoy
hacker       165  0.0  0.0 230696  2560 pts/0    S+   12:23   0:00 grep --color=auto /challenge/decoy
hacker@processes~killing-misbehaving-processes:~$ kill 142 | kill 165
bash: kill: (165) - No such process
hacker@processes~killing-misbehaving-processes:~$ /challenge/run
Sending the flag to /tmp/flag_fifo!
```
<img width="1066" height="376" alt="image" src="https://github.com/user-attachments/assets/cc239cbb-60e9-4623-a4ea-7d4acb3b66db" />


> Terminal 2
```bash
hacker@processes~killing-misbehaving-processes:~$ cat /tmp/flag_fifo
pwn.college{I3Bw.CyaoZrixzwe1Zp.yssMgt2pfsEQGB.V0RkVCf6xvp}
pwn.college{19zWQvr55T4Sk-dXYFSvEGC097FPuAdLFZdN7M.I1.1vs3}
pwn.college{XRGSGBe6rC1vURoX9heyb9X9ELR-l0gkdCIjZbYIDAT0DD}
pwn.college{VmVRVzHnQrirOyQAxD2HTXHoQx58Vf5APGEvSn35wSkfYq}
pwn.college{PyDawzrlNrH7p2J4OHb4L1a.hKWvfd3XX9CmMKVzDkasuC}
pwn.college{KleGkdUlyAQQ5pBOoa7siv4JUzZo6R1usuCNA8WX9RyifN}
pwn.college{T2DDdVDOKFjsolIsEJlLkhx-GaWzc9O92.uPTNhIoYznfA}
pwn.college{qwS2CmS9xkPNNbFZ3-SMYPnrvlWchMoXvtioHxG3rhYnjw}
pwn.college{W69j53oa8FtpUmEC1Hdi54ZMU8ygY2ynTOm8lM7UGHsFZ3}
pwn.college{oRNIC-SqdEvO6M2Az28Iq2U.jTmZOmELvhb7ufK6evS2Ba}
pwn.college{.DbrBrjkizYIniahHnmBhw-tARNcIawXHrI8.VyaIcKODZ}
pwn.college{Tw68N5oVsP3hxJqq4ZzFlOajg1gyiJxYtBhzTIIq-PCuv2}
pwn.college{PS7C-nXxFmlnda5rWTtmtRXASfDLyuwgbfNflP6iMWRLfk}
pwn.college{EDHLfzvLbkR7WEYabypmo.AQLRR5MiN-VRzeBti61MQSaa}
pwn.college{KBjGBKIuW3MJT8uce0JYqUxVnafuw84mSXPzUel7.e8IE2}
pwn.college{QLsFAfHpgY1e7unr1B9im-cLz7iqa3I9suM29K8GcvY66a}
pwn.college{j8zz6D8UqRyyoRzChw0wUTJDEtmOgN7teXzjtr7BhBDbK8}
pwn.college{oDhBty6l-KKJJSYXBuxkCr-XdP2tdOCs1-8X01CsXd8zfk}
pwn.college{f.3JZdkpab7VGkH63LUgLYf5qp4bkU0k2qYd7xlgo62k0z}
pwn.college{TB9dJUe5MD5-CCTh4vLNsmACgRkSBn2syCeu.028hxwwXg}
pwn.college{Hgcq3dNpQtC2cgXnklBDADUrXThN3i0a1wXtyyeIF1EQt4}
pwn.college{2SN8XUJaWf83G7OWKJukY8uv.rhcOZVetWXYZHAatGdlgS}
pwn.college{y.BuVzD62x5f15DZFct5MZYk8tY0wxO7qappVXMJH7u6bV}
pwn.college{Nb04kFTT51EKPzJjsECchscHAB4EEh1eOj4la17iPJNw66}
pwn.college{9KfIXDeT3ScMyBG5m.KhI-SrHCJ0lNskSihMK-ZlTXHbMn}
pwn.college{zpHpnmIBfK3NJ0yQMBEuOgVu7CBMfOgcxpGTSOAqsIzA--}
pwn.college{vcdKIU1zVkrGahyz317gnrvFAb1wjhMAh.QFPs2Wa9Nad3}
pwn.college{GYSd8LRjzsFLURvaj4ENQYcBbpYUPwdYeLd1CRvQrODuzU}
pwn.college{HA2QmUaXbX2nvw1YcD2FY9eZomqgJU6elKU-lVE.fLRNkk}
pwn.college{P5VQaFT1Lu3HawgTgDkf1pUlC8ocV-3urWMEXOkZ0KsVmg}
pwn.college{OVGvu8TYAshVXOuuTHw.mOA-.eKsrtBV1-FFFhijGdPnrX}
pwn.college{H2lWf-HF5Qcyceb6-VdiccCXZQ-Mf7DpmKDJ1WMVr6hp-1}
pwn.college{a3gOL84YISkxCIajisMp745CgAXCKCJ9IX77sgTmscfFZs}
pwn.college{WQS9ueH9LP7NrfKbeq3qdhCpAsotkeAQaYDjXs0guaZzLB}
pwn.college{z0kG2b5Snbjg8cO2m6I2jPjOgSG1CjzSomfYjwgDyaThWg}
pwn.college{hbvvxrmFIghkc3SGs.Had4eTifybytLoJYijOswZkHAk4J}
pwn.college{R9N13MvV7ULHYLp0XEdoidRnX2U909U0oJxaHKnlwj2lg5}
pwn.college{1ijcr.UlMUnf6-.ynQZpL.gBGr4Y3RsIenSalOJiNBB4EB}
pwn.college{6IhpYxa-SkCLnGRCSpBy4AbIrEzozaGMRzEdvTu9SyPmS8}
pwn.college{W8xbkxwDrqoX27gCt-F32sl5e3N8wMwCGn8bpxBAqg7801}
pwn.college{NSqLfxSoRjmE.r0a8X8MdrvRBBNMvIfl03tDcwTwTvlJwu}
pwn.college{C7YVEnm1uF7mZoducMriVDyIR7K8ehjbCjUGqjgdy.P8Kk}
pwn.college{i1xUb-jEY2x8esTxszh1HE-V5wnobNdVORaTNYbtjP9HRJ}
pwn.college{0y4T5XA1DFcws6c1RjDaOPdsFXQ8HKf2qTxOjbsO23hPNN}
pwn.college{mp1N..gkzo9en1e9bnT96uY0Wr0Rcfh7x0k4QkMa7Qgqwb}
pwn.college{CEs4kD54st3DtmUITU019ZIG1R1y97blSU0MP6JBupcVQD}
pwn.college{33mB7r839r-.LsTNmI9lfWWNircUBLDnXxsA.p8gjntLqJ}
pwn.college{bJda3pkGlsiyswSZqeYkyK619FfGyp-fHUU0jHsfjTOLhX}
pwn.college{vZci6Rm0PsGrheY7YpaqD1txk787t7SPBhfnP-QJ8jwCBD}
pwn.college{zB8.R1lEMjXxV8Pcia00usrfeZdQM2.ZKExKEK2hXHj.0l}
pwn.college{zNqt72VQMzKH6d14IS77o31tSCaWE9DDw9Gl7U8yj.jBpT}
pwn.college{B44w9bGYCGxau-YsIYg0g0YboLVOaT.w8oenBryvczmGHK}
pwn.college{uVPQ-h7xHIzD24zvFq9RQus4ERjqJKZE3VtMVh7e5Esm4y}
pwn.college{5YeCKqX5uoZ.hdcj8sF5yQGBLt5w-mMPYQJxMn6RJQGWa0}
pwn.college{KIR2pdK3rHKiJuK4QUJvJMtqQQbZgzm9pnX9UeHifKMlMw}
pwn.college{zhtL.WNjBfBiacuHbZzAuwYf8MC8TnTjg5PLb6RtSkFzb0}
pwn.college{l6xq6wn80eTchFecLhSgQ0RJiSLr.HGTKplGuMpYO3Iwnd}
pwn.college{oQTitBpELwttT.o8kNJj13j25a8tJHawoeWQz6h.a6Y-Y7}
pwn.college{xH9eQvGlE-zzsyi9AkiJhrJ5E76GXZWhJXEAhLmZPwXyL4}
pwn.college{nPN7f6grnCz11Q-7kdclS7Jd5P5PWYzUusB1dVhruiHBpg}
pwn.college{MtUfRlGza-4jryEifPj8jbyA-DF2RmtOoJWav1UrJCL1KJ}
pwn.college{Nd2n-2dJMJSz.XVssCUWhmVaAQfhBAK6NzPVF0mi.DTBvM}
pwn.college{xoHTpLRejOFTYlU4N5X2Etn4ZgwQidZ6zFXzlQ0rz3ehjs}
pwn.college{njn1t9iCQ2P0PWoW3nErPj8hd4AKgLSYO30Da433eG9h91}
pwn.college{QoR0nnyjtaNYNk-X7UaWWlDKrCiW3MLhdLticBotPTEt15}
pwn.college{mbzYW7L9CfsSwfHubBzn481nDl.cx-GB8TWPrOnDTtQrN8}
pwn.college{BpZlKqslTzMdLPCcEyZ2kKJMjvNdJdJIXOMg40CWd-CwcF}
pwn.college{EjwKPr3zYTr1VM7FO4girfZpwWliUZxO5UCXJCStBiY2N7}
pwn.college{-2MJBRffeaJLaxLIKv-dkd1L9y6xKPVH3lr5yEa0XCYS2X}
pwn.college{-Vm41EBQEP7CKkimSVufLX767yoekYH1G4oQ-fkXhMmpdZ}
pwn.college{4wJlXkv2KSTOFpeWps6ccRpc-Mw3RfPkLt9pRZgbiQij5Y}
pwn.college{HjljnoWIa2AkwGqvXUqm5Ck3HtSkzZOWPNDXxLh6N-Sp2c}
pwn.college{KiQd51vv-1ZlhfIHD9Bypvp2XlVW2h6x2TzdYBYTINhKBj}
pwn.college{lRRfpS1ub6BKh4m7Trrzrr-zy0OfpZoLqRH.NqRN0W84.S}
pwn.college{n0pEq8oRx0ROwIyePlUZKLFh.VRWG2Bgl.i.sXnnXdqrCl}
pwn.college{bgA0ByA3l3Kh0eTEUcSTn6TOsq.sQWGnX9rP0qJb9uc9Aa}
pwn.college{wZ-w.kFC.U8U0Xh-cHYNNolomHRf7hgVMfJvhbn3JA5Gnw}
pwn.college{ko03459yUkwmppCvBg.AIqYX6oB09VS20w7oOdVETYhvBx}
pwn.college{aUXy6Xa6MUQP6EqKx5IgDkZAPbfzXlL39uhm.PtKl1Ccfg}
pwn.college{iSS2DQe1YpBAzzJIkANLJ9fyiEij8nTcdhVbhIeHWXHVHM}
pwn.college{93fwXHQ7-I-3VYsM1pbblqZShcHaacU4kA41ALWuvTjzma}
pwn.college{OuRSIkFeQZGNcY3PwL30LfneWsK036yq5sqo6gZpuxS6Pb}
pwn.college{MRde5nzU3kKvPBRwrpW42SeWrh-3qNaFDikA-guNJ0dkaH}
pwn.college{Wc-txJFvNpf4PGpOsFXDOng1tFiS7gUX8FG3XtAOn.AJuC}
pwn.college{yBCgq3f.ZrmdJYQ5lTVuFkXcnwHq-Ye8znVDLlgpCw4Zj2}
pwn.college{BBuChsEHDjGW8CUIMMNFdLLgQtY.tV.a8mXzpndnsQr5GS}
pwn.college{92Hn-QmtKcJY6LKbGH5BcXs9XvXrd4owdBaTfMVriDLVza}
pwn.college{sGZ3erQh1QBq27hxQNe6QrfHynPBnh0x88.C8XJpx-jvNl}
pwn.college{BAV8h5bQkrP1n8FnmtvCuV.ZiRX4667mQqMxb3speESdgJ}
pwn.college{pEBIHt2xNFLdU-qCy5Rwi79OIxuULa1LNsctzmCoNt2rgs}
pwn.college{L5GJSjAuhZStAhZ-DG2H0B2AI5Z0vuET2piTkypiiM6nAF}
pwn.college{Mu431MWnqU.M4q12Fk6o2qlyReswaWkvlkzRawzu4cucWh}
pwn.college{G3-ZP8ZlYCHJvHCG0qE7uMkvaUVoSw3TVFGSW3LpwaaiBN}
pwn.college{-Voh.WEZJzykVnmzZnZfKDipFPXnphQX5DB29foCeYOmUj}
pwn.college{Wcq4j0fv7q-L056UnRKs2opX7UZfyKmELr2RstqInY5U-b}
pwn.college{kehRED.9jgae06bAaA1Y-KMUToqDKhzuaWlw5dsBvz6PEU}
pwn.college{XFG8btKZVWZZ1KhryvzEvFqrsaOTBHqFTxK1AaaEmOCah6}
pwn.college{Qj4OkHbbbAwO6eJWGrWFK415JXCgoJiTPLl07-.S9VifBn}
pwn.college{2bDXeH.zI4qd9sWQE68ToShcNhdxe.tR4gvKEWPVxkKcrN}
pwn.college{0iy3JyK-ZEA0Kxt.wQGqL49sLXxn5vInuy-8i7xunfkA-W}
pwn.college{RLvikWN46IrN8vatFCcbAKZP.5GvtV8ReSUTZ7zivn5cXh}
pwn.college{IfPwiEhDGPqUeu.Xe8gvzDVy2e8TTaS3Is6hIgav974m5E}
pwn.college{dATf37Iq.dlGFQuwpR5MzDWdZg80dSnUQlXk3DS-XSSu2h}
pwn.college{B4bsTikMib9as4j2oXTB1grB-.cKujz0gqPBdU9I-2ZC8q}
pwn.college{hM1EwZRyO0.e1-BkaknkH8oTfCsxTEZBvpn.mQbSpoVfrc}
pwn.college{Q8jXwQTaHt4ri7PA7VszAKiM7Rm38rdcaGQpKkqXR1WFH2}
pwn.college{wAnFmmzrfNFGuljHufuQczF29LBQ.PgyFJRRSmPfTL0laI}
pwn.college{kMH0qzWG2TZsiSL2Eu85Lv2tQaayOFRvbxigHG9ktI2tdu}
pwn.college{f3Sk94ror3fEVWBR3w0IaZWpc2Yc625ZkLNl.3MKXLFLtb}
pwn.college{9IFeh7kMlu.Fba1GydsjkVHDQEXsP1CAEpSuveKr8FmQBS}
pwn.college{VRnC76CTHnPlGXbZti22SD7PQ8Ap5S2Klxlcipq2JrXo-r}
pwn.college{x8yGL94JS-CWXpgedq0Sco4.82BSRXRvkLAcVoFR6whXzh}
pwn.college{NJODdpKcnTFmWJJ5fo2CN.5O.vUj3ntt3YXS24-ZiWc91z}
pwn.college{BFvIxX9LOltjJMhyvgJrqr.DcA0slahl3WkRL3GwFSFVbY}
pwn.college{VLOlGxl6KJnYSlju.Sf6YJjsW.HPSsdMgNE9F5lH3Q41Bc}
pwn.college{hxUKZ0jvERxLeDbzYMxJbQbyuw14LHHsb9P0.3mceSI6kz}
pwn.college{JuNgcRSFwCzY1PX3LVqxJowv-bFE57TVb4K.AwmaFpoaG2}
pwn.college{TH.MYTLpHC50Fn3s3tOmGmj8MVzZhmcD7b.-mVMuiEA5bJ}
pwn.college{Db5lEWlvnWRpyOPmkInn4INAmVNVN8OyaVx6g7teeDqi53}
pwn.college{8nIIV6zZFq.eqOYHq88YQSkPjnMeMYFlOlQCVMXBfN857k}
pwn.college{60I44Og9d4W4ntS4k1GCyDZM2LnqLUwVFFQXy9hJxzq7wG}
pwn.college{b9JfS1V0rwWzCMRHrg8tNInCl2I.2u26RqKH0FEpliNA.H}
pwn.college{E05y3j0vClS-UbR8fDN0hnvOgHzBNNfR68UOS8MefCGwgb}
pwn.college{n0GPrCLNG2RQGcBZgnE5U73MnX9Cfrbw-LLAYoC6riN37H}
pwn.college{STVfTjP3WfGZjL0fVtix22k1KkMB50dtEYNCjOD6rmYKaf}
pwn.college{7Sh71a5dhKQIAi1gfa92.NbHDQnWsVH.nQEJTCmHxBzrNN}
pwn.college{v1L.VXhLZmvrhULw1RSow58JPmXdpuug.EQ8DfXUYVhDvG}
pwn.college{0aqc0LlubEWzoG1TZIzd30.cLsATAuBWmipZN4Eck-OYlz}
pwn.college{fguPXwdszWx0AIQG0Uta26JfHVCuN1c7C0FJGjrqX.h-PT}
pwn.college{-vVBgabeMEoAOmPhwfGJT4FqSZqk81nTEm7k64QwdARMUh}
pwn.college{EXvuCkm3RtKUbYQaWxnytEaLolnPydh1o3d8S3O9srdFDd}
pwn.college{uYF9CZXR3-CEM64oiRVmwFGDIscSbJ0-hcOArWqitAGlC2}
pwn.college{uxV19I4Sna4K35PXqF4I2fS6DuEyjyPrYyuepcWBI5vtfr}
pwn.college{3ElyYon9M2rdbLhfjjgN3X-gR-EUICXqKk.XJl6qJx7-8h}
pwn.college{F5Gymh85CLICuUd-bFO-24.E2Rlg16LBTbeKGR-tUB9qV0}
pwn.college{37a9Burt.pDpO6a9RJs1v6ri4e7iIqAPoKUQhFGJj5iEPl}
pwn.college{EaaE5L_YPfWg4hAzcM4dYlc8jFS.QX0MzM4EDL5EzN0czW}
```

> [!NOTE]
> Apparently there is docker issue for my pwn college for this particular program, so I can skip this one as allowed by my mentor Harshith.
**Flag:** `pwn.college{}`
## New Learning
## Reference
