---
title: 보고 레이블 추가 및 업데이트
author: tonysmit
ms.author: tonysmit
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 실제 위치 및 관련 서브넷 목록이 포함 된 텍스트 파일을 업로드 하 여 보고 레이블을 추가 하 고 업데이트 하는 방법에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.locations.reportinglabels.overview
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.location
- ms.teamsadmincenter.locations.overview
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b245566c0920604dac0e10e6a6cfe49937570bc2
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137118"
---
<a name="add-and-update-reporting-labels"></a>보고 레이블 추가 및 업데이트
============================

보고 레이블은 조직에서 사무실, 건물 또는 조직 사이트의 실제 위치를 나타내는 데 사용 됩니다. Microsoft 팀 관리 센터의 보고 레이블 페이지에서 실제 위치 및 관련 네트워크 서브넷 목록을 포함 하는 텍스트 파일 (.csv 또는 tsv)을 제공할 수 있습니다. 이 파일은 통화 분석 및 보고서 생성을 위한 통화 품질 대시보드에서 사용 합니다. 서브넷 매핑을 업로드할 때 이러한 서비스에서 제공 하는 보고서에는 위치 이름도 포함 되며, 이러한 보고서를 이해 하 고 수정 하는 데 사용 하는 것이 더욱 쉬워질 수 있도록 합니다.

제공 하는 보고서 레이블 및 위치 데이터는 단일 데이터 구조 이며 현재는 데이터를 개별적으로 편집할 수 있는 인터페이스가 없습니다.

**서브넷 및 위치 표 편집**

1. Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **위치** > **보고 레이블을**클릭 합니다.
2. **위치 데이터 바꾸기를**클릭 합니다.
3. **위치 데이터 바꾸기** 창에서 **파일 선택을**클릭 한 다음 편집 된 .csv 또는 tsv 파일을 찾아 업로드 합니다.
4. **업로드**를 클릭 합니다.

[여기](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)에서 샘플 서식 파일을 다운로드할 수 있습니다.

다음 예제를 사용 하 여 데이터 파일을 만들 수 있습니다.

> [!IMPORTANT]
> 데이터 파일에는 열 머리글 (예: 네트워크, 네트워크 이름 등)이 포함 되지 않아야 합니다. 이는 정보 제공 목적 으로만 사용 됩니다. <br>

|네트워크|네트워크 이름|네트워크 범위|건물 이름|소유권 형식|건물 종류|Office 유형 빌드|곳|우편번호|명칭|상태|지역|내부 회사|Express 경로|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso의 임대 다시&F|Office|다시&F|산 보기|94043|보세요|캐나다|보세요|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso의 임대 다시&F|Office|다시&F|산 보기|94043|보세요|캐나다|보세요|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso의 임대 다시&F|Office|다시&F|산 보기|94043|보세요|캐나다|보세요|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso의 임대 다시&F|Office|다시&F|산 보기|94043|보세요|캐나다|보세요|1|1|

데이터 파일의 서식을 지정 하는 방법에 대 한 자세한 내용은 [테 넌 트 데이터 파일 형식 및 빌드 데이터 파일 구조](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-structure)를 참조 하세요.

## <a name="related-topics"></a>관련 항목

[통화 분석 설정](set-up-call-analytics.md)
