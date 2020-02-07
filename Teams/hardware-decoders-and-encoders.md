---
title: 하드웨어 디코더와 인코더 드라이버 권장 사항
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/06/2019
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-voice
localization_priority: Normal
search.appverid: MET150
description: 드라이버 문제로 인해 하드웨어 가속을 사용할 수 없는 운영 체제, 모델 및 드라이버의 조합을 나열 합니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: dace536d8d47ecacc15661d159563a916b447113
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836438"
---
# <a name="hardware-decoder-and-encoder-driver-recommendations"></a>하드웨어 디코더와 인코더 드라이버 권장 사항

Microsoft는이 문서에 나열 된 모든 디코더와 인코더를 지원 합니다.

## <a name="hardware-decoder-driver-recommendations---intel"></a>하드웨어 디코더 드라이버 권장 사항-인텔

다양 한 드라이버 문제 때문에 다음 운영 체제, 모델 및 드라이버 조합은 하드웨어 가속을 사용 하도록 설정 되어 있지 않습니다.

|운영 체제           | 모델 (Device_id) | 드라이버/범위 |
|---------------------------|-------------------|--------------|
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0116 | [2, 0, 11929] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0126 | [0.0.0.0]-[8.15.10.2418] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 모든 | [0.0.0.0]-[8.15.10.2753] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x2772 | [8.15.10.1749] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0162, 0x0162 | [0.0.0.0]-[9.17.10.2850] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 모든 | [9.17.10.2867] - [9.17.10.4459] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 |0x1616 | [9.18.7.9] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 모든 | [10.18.10.3431] - [10.18.10.4425] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 모든 | [10.18.14.4280] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x1616 |[10.18.15.4256] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x1916 |[10.18.15.4293] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 모든 |[10.18.15.4281] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 모든 |[20.19.15.4390] - [20.19.15.4444] |
|Windows 10 | 모든 | [21.20.16.4541] |
|Windows 10 | 모든 | [22.20.16.4811] |
|Windows 10 | 모든 | [24.20.100.6293] |

## <a name="hardware-decoder-driver-recommendations---nvidia"></a>하드웨어 디코더 드라이버 권장 사항-Nvidia

다양 한 드라이버 문제 때문에 다음 운영 체제, 모델 및 드라이버 조합은 하드웨어 가속을 사용 하도록 설정 되어 있지 않습니다.

|운영 체제           | 모델 (Device_id) | 드라이버/범위 |
|---------------------------|-------------------|--------------|
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0540 | [8.15.1.1243] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0A20 | [8.15.11.8627], [8.15.11.8634], [8.15.11.8642] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0A34 | [8.15.11.8631], [8.15.11.8636], [8.15.11.8652], [8.15.11.8662], [8.15.11.8664], [8.16.11.8691] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0A74 | [8.15.11.8636], [8.15.11.8652], [8.15.11.8688] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0A28 | [8.15.11.8644] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0A69 | [8.16.11.8691] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0A3C | [0.0.0.0]-[8.17.12.6721] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0873 | [8.17.12.8562] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x040C, 0x0429, 0x06FD | [0.0.0.0]-[8.17.12.9670] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 모든 | [8.17.11.9745], [8.17.12.5738] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0A2B | [0.0.0.0]-[9.18.13.282] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x087D | [9.18.13.697] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x1040 |[0.0.0.0]-[9.18.13.1106] |
|Windows 10 | 모든 | [10.18.13.5891] - [10.18.13.6881] |
|Windows 10 | 모든 | [21.21.13.6909], [21.21.13.7570] |
|Windows 7 | 모든 | [21, 21, 13, 4201] |

## <a name="hardware-decoder-driver-recommendations---amd"></a>하드웨어 디코더 드라이버 권장 사항-AMD

레거시 운영 체제의 경우 하드웨어 가속에는 다음 Device_ids만 사용할 수 있습니다.

|운영 체제           | 모델 (Device_id) |
|---------------------------|-------------------|
|Windows 7/<br>Windows 8/<br>Windows 8.1 | 0x9874, 0x9851, 0x9853, 0x9854, 0x9855, 0x9856, 0x9857, 0x9858, 0x9857, 0x9858, 0x9859, 0x985A, 0x985B, 0x985C, 0x985D, 0x985E, 0x985F, 0X9874, 0X9874, 0X9874, 0X9874, 0x67C4, 0x67C7, 0x67D0, 0X9874, 0X9874, 0x67E0, 0x67E1, 0x67E8, 0x67E9, 0X9874, 0X9874 0x67EF, 0X67ef, 0x67ef, 0x67ef, 0x6900, 0X6963c, 0X67ef, 0X67ef, 0x6860, 0x67ef 0x67ef, 0x67ef, 0x6864, 0x67ef, 0x67ef, 0x67ef, 0x686A, 0X67ef, 0x686C, 0x686D, 0x686E, 0x687F, 0X67ef, 0X67ef, 0x69A2, 0x69A3, 0X67ef, 0x66A0, 0x66A1, 0x66A2, 0x66AF |

다양 한 드라이버 문제 때문에 다음 운영 체제, 모델 및 드라이버 조합은 하드웨어 가속을 사용 하도록 설정 되어 있지 않습니다.

|운영 체제           | 모델 (Device_id) | 드라이버/범위 |
|---------------------------|-------------------|--------------|
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 모든 | [0.0.0.0] – [25.20.15017.1009] |

## <a name="hardware-encoder-driver-recommendations---intel"></a>하드웨어 인코더 드라이버 권장 사항-인텔

다양 한 드라이버 문제 때문에 다음 운영 체제, 모델 및 드라이버 조합은 하드웨어 가속을 사용 하도록 설정 되어 있지 않습니다.

|운영 체제           | 모델 (Device_id) | 드라이버/범위 |
|---------------------------|-------------------|--------------|
|Windows 7 | 모든 | [8.15.10.2200] - [8.15.10.2600] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 모든 | [8.15.10.2653] - [8.15.10.2827] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 모든 | [9.14.3.1176] - [9.14.3.1177] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 모든 | [9.17.10.2800] - [9.17.10.9999] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 모든 | [9.18.10.3222] |
|Windows 7 | 모든 | [9.18.10.3234] |
|Windows 7 | 모든 | [9.18.10.3272] |
|Windows 7 | 모든 | [10.18.10.3242] - [10.18.10.9999] |
|Windows 8/Windows 8.1/Windows 10 | 모든 | [10.18.10.0000] - [10.18.10.9999] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 모든 | [10.18.14.4153] - [10.18.14.4161] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 모든 | [10.18.14.4264] |
|Windows 7 | 모든 | [10.18.14.4578] |
|Windows 7 | 모든 | [10.18.14.4889] |
|Windows 7 | 모든 | [10.18.14.5057] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 모든 | [20.19.15.4300] - [20.19.15.4444] |
|Windows 7 | 모든 | [20.19.15.4474] |

## <a name="hardware-encoder-driver-recommendations---nvidia"></a>하드웨어 인코더 드라이버 권장 사항-Nvidia

다양 한 드라이버 문제 때문에 다음 운영 체제, 모델 및 드라이버 조합은 하드웨어 가속을 사용 하도록 설정 되어 있지 않습니다.

|운영 체제           | 모델 (Device_id) | 드라이버/범위 |
|---------------------------|-------------------|--------------|
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 모든 | [0.0.0.0]-[21.21.13.7848] |

## <a name="hardware-encoder-driver-recommendations---amd"></a>하드웨어 인코더 드라이버 권장 사항-AMD

레거시 운영 체제의 경우 하드웨어 가속에는 다음 Device_ids만 사용할 수 있습니다.

|운영 체제           | 모델 (Device_id) |
|---------------------------|-------------------|
|Windows 7 | 0x9874, 0x9850, 0x9851, 0x9852, 0x9853, 0x9854, 0x9855, 0x9856, 0x9857, 0x9858, 0x9859, 0x985A, 0x985B, 0x985C, 0x985D, 0x985E, 0x985F, 0X9874, 0X9874, 0x67C1, 0X9874 t, 0x67C5, 0x67c10, 0x9874/c f 2, 0x67C7, 0x67C8, 0x9874 10/f 6, 0x67 Ca, 0X9874, 0X9874, 0X9874 0x67CE, 0X67ce, 0x67D0, 0X67ce, 0X67ce, 0x67D3, 0X67ce, 0X67ce, 0x67D6, 0x67D7, 0x67D8, 0x67D9, 0X67ce, 0X67ce, 0X67ce, 0X67ce, 0X67ce, 0x67E0, 0x67E1, 0X67ce, 0X67ce, 0x67E4, 0x67E5, 0x67E6, 0x67E7, 0x67E8, 0x67E9, 0X67ce, 0X67ce, 0X67ce, 0X67ce 0x67EE, 0X67ee, 0x67F0, 0X67ee, 0X67ee, 0x67F3, 0x67ee F4, 0x67F6, 0x67ff, 0x67F7, 0X6717f8, 0X67ee, 0X67ee 0x67FB, 0X67ee, 0X67ee, 0X67ee, 0X67ee, 0x1306, 0x1305, 0x117, 0x1309, 0X117a, 0x1305, 0x130a, 0x130B, 0x130C, 0x130D, 0x130E, 0x130F, 0x1310, 0x1311, 0x1312, 0x1312, 0x1312, 0x1312, 0x1312, 0x1317, 0x1312, 0x1312, 0X1312, 0X1312, 0X1312 0X1312, 0X131:, 0X1312, 0x66A0, 0x66A1, 0x66A2, 0x66A3, 0x66A4, 0x66A7, 0x66AF, 0x1312, 0x6861, 0x6862, 0x6867, 0x6868, 0x60x6869, 0X60x6867b, 864 6A 0x686E, 0x687F, 0x69A0, 0X69a, 0x69A2, 0x69A3, 0x69AF

다양 한 드라이버 문제 때문에 다음 운영 체제, 모델 및 드라이버 조합은 하드웨어 가속을 사용 하도록 설정 되어 있지 않습니다.

|운영 체제           | 모델 (Device_id) | 드라이버/범위 |
|---------------------------|-------------------|--------------|
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x674a | [0.0.0.0] – [99.9999.9999.9999] |
|Windows 7 | 모든 | [0.0.0.0]-[16.199.9999.9999] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 모든 | [15.21.0.0] - [16.199.9999.9999] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 모든 | [15.201.1101.0] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 모든 | [21.19.137.1] |

## <a name="related-topics"></a>관련 항목

[Teams 앱의 하드웨어 요구 사항](hardware-requirements-for-the-teams-app.md)
