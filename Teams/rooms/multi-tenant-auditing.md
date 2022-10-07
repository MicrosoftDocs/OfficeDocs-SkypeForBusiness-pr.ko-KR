---
title: MTR Pro 포털에서 감사 로깅
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: MTR Pro 포털에 대한 감사 로깅입니다.
f1keywords: ''
ms.openlocfilehash: 0436618e257128deb38d890cb92813ae13921e7d
ms.sourcegitcommit: 64c01699022b47fdfec8dc6e2ca279e57eae3baa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68243919"
---
# <a name="audit-logging-in-the-mtr-pro-portal"></a>MTR Pro 포털에서 감사 로깅

MTR Pro 포털의 감사 로그를 사용하면 사용자 및 관리자가 수행한 활동에 대한 감사 레코드를 검색할 수 있습니다. 이 기능은 기본적으로 사용하도록 설정됩니다. 관리 서비스 관리자만 로그를 내보낸 다음 볼 수 있는 권한이 있습니다.

> [!NOTE]
> MTR Pro 포털에서 수행된 작업은 Microsoft 365 또는 Office 365 감사에 기록되지 않습니다. 

## <a name="exporting-logs"></a>로그 내보내기

감사 로그 검색에 대한 모든 결과를 내보내면 통합 감사 로그의 원시 데이터가 로컬 컴퓨터에 다운로드된 CSV(쉼표로 구분된 값) 파일로 복사됩니다. 

**로그를 다운로드하려면** 

1. **설정 > 일반 > 감사 로그로** 이동합니다.
1. 관심 있는 로그의 날짜 범위를 정의하려면 **시작 날짜** 와 **종료 날짜를** 입력합니다.

   > [!NOTE]
   > 로그는 최대 180일 동안만 사용할 수 있습니다.

1. **로그 다운로드를 선택합니다.**

   ![감사 로그 날짜 범위](../media/multi-tenant-auditing.png)

   창 아래쪽에 표시되는 메시지는 CSV 파일을 열거나 저장하라는 메시지를 표시합니다. 

1. **다른 이름으로 저장** > 을 선택하고 CSV 파일을 로컬 컴퓨터에 저장합니다. 

1. 모든 활동을 검색할 때 또는 광범위한 날짜 범위에서 많은 검색 결과를 다운로드하는 데 시간이 걸립니다. CSV 파일 다운로드가 완료되면 창 아래쪽에 메시지가 표시됩니다.

## <a name="detailed-properties-in-the-audit-log"></a>감사 로그의 자세한 속성

다음 표에서는 CSV에 포함된 속성을 설명합니다.

|속성|설명|
| - | - |
|activity.category|<p>동작이 수행된 개체의 범주입니다. 가능한 값:</p><p>**사용자, 할당, PartnerInvitation, 역할**</p>|
|activity.objectName|수정된 개체의 이름입니다.|
|activity.operation|수행된 작업의 유형입니다. 가능한 값은 **만들기, 업데이트, 삭제** 입니다. |
|activity.resultStatus|<p>작업( **activity.operation** 속성에 지정됨)이 성공했는지 여부를 나타냅니다.</p><p>값은 **성공** 또는 **실패입니다**.</p>|
|activity.tenantId|작업이 수행된 테넌트 GUID|
|creationTime|사용자가 활동을 수행한 경우 ISO 형식의 UTC(협정 세계시)의 날짜와 시간입니다.|
|user.userId|레코드가 기록되는 작업을 수행한 사용자입니다.|
|user.userTenantId|작업을 수행한 사용자의 테넌트 GUID|


