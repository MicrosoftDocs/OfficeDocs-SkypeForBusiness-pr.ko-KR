---
title: Education SKU 참조
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: karsmith
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 교육 교직원 및 학생 라이선스 계획 및 SKU 신분을 나열합니다.
f1keywords: ''
ms.openlocfilehash: dc8b476e4af134199fe402c998a20dbd84d0919d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834248"
---
# <a name="education-sku-reference"></a>Education SKU 참조

이 문서에는 PowerShell을 사용하여 라이선스 유형별로 조직의 사용자를 식별할 때 참조로 사용할 수 있는 SKU(Education 교직원 및 학생 라이선스 계획) 및 SKU가 나열됩니다.

## <a name="faculty-licenses"></a>교직원 라이선스

|계획 이름 |SkuPartNumber   |SkuID |
|---------|---------|---------|
|교직원용 Office 365 Education E3     |ENTERPRISEPACK_FACULTY         |e4fa3838-3d01-42df-aa28-5e0a4c68604b         |
|교직원용 Office 365 Education       |STANDARDWOFFPACK_FACULTY        |94763226-9b3c-4e75-a931-5c89701abe66         |
|교직원용 Office 365 Education       |STANDARDWOFFPACK_IW_FACULTY     |78e66a63-337a-4a9a-8959-41c6654dfb56         |
|교직원용 Office 365 Education E5    |ENTERPRISEPREMIUM_FACULTY       |a4585165-0533-458a-97e3-c400570268c4         |
|교직원용 PSTN 회의가 없는 Office 365 Education E5      |ENTERPRISEPREMIUM_NOPSTNCONF_FACULTY         |9a320620-ca3d-4705-a79d-27c135c96e05         |
|교직원용 Office 365 Education E1     |STANDARDPACK_FACULTY         |a19037fc-48b4-4d57-b079-ce44b7832473         |
|교직원용 Office 365 Education E3     |ENTERPRISEPACK_EDULRG         |f5a9147f-b4f8-4924-a9f0-8fadaac4982f         |
|교직원용 Office 365 Education E4      |ENTERPRISEWITHSCAL_FACULTY         |16732e85-c0e3-438e-a82f-71f39cbe2acb         |
|교직원용 Microsoft 365 Education A3      |M365EDU_A3_FACULTY         |4b590615-0888-425a-a965-b3bf7789848d         |
|교직원용 Microsoft 365 Education A5       |M365EDU_A5_FACULTY         |e97c048c-37a4-45fb-ab50-922fbf07a370         |
|교직원용 오디오 회의가 없는 Microsoft 365 A5     |M365EDU_A5_NOPSTNCONF_FACULTY         |e578b273-6db4-4691-bba0-8d691f4da603         |
|교직원용 가정용 Office 365 Education     |STANDARDWOFFPACK_HOMESCHOOL_FAC         |43e691ad-1491-4e8c-8dc9-da6b8262c03b         |
|교직원용 Office 365 A1(장치용)     |STANDARDWOFFPACK_FACULTY_DEVICE         |af4e28de-6b52-4fd3-a5f4-6bf708a304d3         |

## <a name="student-licenses"></a>학생 라이선스

|제품 이름 |SkuPartNumber   |SkuID |
|---------|---------|---------|
|학생용 Office 365 Education E3       |ENTERPRISEPACK_STUDENT         |8fc2205d-4e51-4401-97f0-5c89ef1aafbb         |
|학생용 Office 365 Education     |STANDARDWOFFPACK_IW_STUDENT         |314c4481-f395-4525-be8b-2ec4bb1e9d91         |
|학생용 Office 365 Education E5      |ENTERPRISEPREMIUM_STUDENT         |ee656612-49fa-43e5-b67e-cb1fdf7699df         |
|학생용 PSTN 회의가 없는 Office 365 Education E5     |ENTERPRISEPREMIUM_NOPSTNCONF_STUDENT         |1164451b-e2e5-4c9e-8fa6-e5122d90dbdc         |
|학생용 Office 365 Education E1       |STANDARDPACK_STUDENT         |d37ba356-38c5-4c82-90da-3d714f72a382         |
|학생용 Office 365 Education E4      |ENTERPRISEWITHSCAL_STUDENT         |05e8cabf-68b5-480f-a930-2143d472d959         |
|학생용 Microsoft 365 Education A3      |M365EDU_A3_STUDENT         |7cfd9a2b-e110-4c39-bf20-c6a3f36a3121         |
|학생용 Microsoft 365 Education A3 사용 혜택       |M365EDU_A3_STUUSEBNFT         |18250162-5d87-4436-a834-d795c15c80f3         |
|학생용 Microsoft 365 Education A5        |M365EDU_A5_STUDENT       |46c119d4-0379-4a9d-85e4-97c66d3f909e        |
|Microsoft 365 A5 Student 사용 혜택     |M365EDU_A5_STUUSEBNFT         |31d57bc7-3a05-4867-ab53-97a17835a411         |
|학생용 오디오 회의가 없는 Microsoft 365 A5      |M365EDU_A5_NOPSTNCONF_STUDENT         |a25c01ce-bab1-47e9-a6d0-ebe939b99ff9         |
|학생용 오디오 회의가 없는 Microsoft 365 A5 사용 혜택    |M365EDU_A5_NOPSTNCONF_STUUSEBNFT         |81441ae1-0b31-4185-a6c0-32b6b84d419f         |
|학생용 Office 365 A3     |ENTERPRISEPACKPLUS_STUDENT         |98b6e773-24d4-4c0d-a968-6e787a1f8204         |
|Office 365 A3 학생 사용 혜택     |ENTERPRISEPACKPLUS_STUUSEBNFT         |476aad1e-7a7f-473c-9d20-35665a5cbd4f         |
|Office 365 A5 Student 사용 혜택    |ENTERPRISEPREMIUM_STUUSEBNFT         |f6e603f1-1a6d-4d32-a730-34b809cb9731         |
|학생용 오디오 회의가 없는 Office 365 A5 사용 혜택  |ENTERPRISEPREMIUM_NOPSTNCONF_STUUSEBNFT         |bc86c9cd-3058-43ba-9972-141678675ac1         |
|학생용 가정용 Office 365 Education     |STANDARDWOFFPACK_HOMESCHOOL_STU         |afbb89a7-db5f-45fb-8af0-1bc5c5015709         |
|학생용 Office 365 A1(장치용)     |STANDARDWOFFPACK_STUDENT_DEVICE         |160d609e-ab08-4fce-bc1c-ea13321942ac         |
|학생용 Office 365 A1 Plus     |STANDARDWOFFPACK_IW_STUDENT         |e82ae690-a2d5-4d76-8d30-7c6e01e6022e         |

## <a name="related-topics"></a>관련 항목

- [학교에서 대규모 사용자 집합에 정책 할당](batch-group-policy-assignment-edu.md)
