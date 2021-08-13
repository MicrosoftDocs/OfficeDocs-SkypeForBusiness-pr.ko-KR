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
description: 물리적 위치 및 연결된 서브넷 목록이 포함된 텍스트 파일을 업로드하여 보고 레이블을 추가하고 업데이트하는 방법을 알아보습니다.
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
ms.openlocfilehash: 0a617cdabba70a836327f6b2153ccecacb5d695040c99007845c79e776e478a1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321330"
---
<a name="add-and-update-reporting-labels"></a>보고 레이블 추가 및 업데이트
============================

보고 레이블은 조직에서 사무실, 건물 또는 조직의 실제 위치를 나타내는 데 사용됩니다. 관리 센터의 Microsoft Teams 레이블 페이지를 사용하면 물리적 위치 목록과 연결된 네트워크 서브넷 .csv 텍스트 파일(.csv 또는 .tsv)을 제공할 수 있습니다. 이 파일은 통화 분석에서 보고서를 생성하는 데 사용됩니다. 서브넷 매핑을 업로드할 때 이러한 서비스에서 제공하는 보고서에는 위치 이름도 포함되어 잠재적 문제를 해결하기 위해 보고서를 더 쉽게 이해하고 사용할 수 있습니다.

> [!IMPORTANT]
> 업로드한 보고서 레이블은 고객 데이터  또는 개인 데이터로 간주되는 Office 365 계약에 따라 지원  데이터로 *처리됩니다.* 지원 데이터로 Microsoft에 제공하지 않을 데이터는 포함하지 않습니다. 이 정보는 지원 목적으로 Microsoft 엔지니어에게 표시됩니다. 

사용자가 제공하는 보고서 레이블 및 위치 데이터는 단일 데이터 구조입니다. 현재는 개별 데이터를 편집할 수 있는 인터페이스가 없습니다.

**서브넷 및 위치 표를 편집하려면**

1. 관리 센터의 왼쪽 Microsoft Teams 위치 보고   >  **레이블을 클릭합니다.**
2. 데이터 **업로드 클릭합니다.**
3. 데이터 **업로드** 창에서 파일 선택을 클릭한 다음 편집된 파일 또는 .tsv .csv 업로드합니다.
4. 를 **업로드** 클릭합니다.

여기에서 샘플 템플릿을 다운로드할 [수 있습니다.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)

다음 예제를 사용하여 데이터 파일을 만들 수 있습니다.

> [!IMPORTANT]
> 데이터 파일에 열 헤더(예: 네트워크, 네트워크 이름 등)가 포함되어 있지 않습니다. 여기서는 정보 제공 목적으로만 사용됩니다. <br>

|네트워크|네트워크 이름|네트워크 범위|건물 이름|소유권 유형|건물 유형|건물 Office 형식|도시|우편번호|국가|상태|지역|Corp 내부|익스프레스 경로|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso 임대 RE&F|Office|RE&F|마운틴 뷰|94043|미국|CA|미국|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso 임대 RE&F|Office|RE&F|마운틴 뷰|94043|미국|CA|미국|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso 임대 RE&F|Office|RE&F|마운틴 뷰|94043|미국|CA|미국|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso 임대 RE&F|Office|RE&F|마운틴 뷰|94043|미국|CA|미국|1|1|

데이터 파일 서식에 대한 자세한 내용은 테넌트 데이터 파일 형식 및 데이터 파일 구조 구축 [을 참조하세요.](CQD-upload-tenant-building-data.md#upload-building-data-file)

## <a name="related-topics"></a>관련 항목

[통화 분석 설정](set-up-call-analytics.md)

[통화 분석을 사용하여 통화 품질 불량 문제 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)
