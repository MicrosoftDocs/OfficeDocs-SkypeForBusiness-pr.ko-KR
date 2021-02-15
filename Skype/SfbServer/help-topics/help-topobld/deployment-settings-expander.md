---
title: 배포 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DeploymentSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7220ec1f-38cb-4297-870e-591a832cd2f2
description: 다음 섹션을 사용하여 기존 배포의 속성을 편집할 수 있습니다.
ms.openlocfilehash: c7a360146f91c2e411ff48f52d92a3c69b0a2e11
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835368"
---
# <a name="deployment-settings-expander"></a>배포 설정 확장기

다음 섹션을 사용하여 기존 배포의 속성을 편집할 수 있습니다.

- SIP 도메인

- 단순 URL

- 중앙 관리 서버

## <a name="sip-domain"></a>SIP 도메인

**기본 SIP 도메인** 을 편집하려면 새 도메인 이름을 입력합니다.

**추가 지원 SIP 도메인** 을 추가하려면 추가해야 할 도메인의 이름을 입력합니다. **추가** 를 클릭하여 해당 도메인 이름을 새 SIP(Session Initiation Protocol) 도메인 이름으로 수락합니다.

기존 추가 SIP 도메인 이름을 업데이트하려면 도메인 이름을 선택하고 텍스트 상자의 내용을 변경합니다. **업데이트** 를 클릭하여 변경 내용을 수락합니다.

정의된 추가 SIP 도메인 이름을 제거하려면 도메인 이름을 선택한 다음 **제거** 를 클릭합니다.

속성 편집 페이지에서 모든 변경을 마쳤으면 **확인** 을 클릭하여 변경 내용을 저장합니다. 변경 내용을 취소하려면 **취소** 를 클릭합니다.

## <a name="simple-urls"></a>단순 URL

단순 URL을 수정하거나 정의하려면 세 가지 단순 URL 중 편집하거나 변경할 단순 URL을 결정합니다. 전화 액세스 URL, 모임 URL 및 관리 액세스 URL 중에서 선택할 수 있습니다.

전화 액세스 URL 또는 모임 URL을 수정하려면 변경해야 하는 URL을 선택합니다. **URL 편집** 을 클릭합니다. 그런 다음 URL을 편집하고 **확인** 을 클릭하여 URL을 저장합니다. 변경 내용을 취소하려면 **취소** 를 클릭합니다.

새 URL을 추가하려면 **추가** 를 클릭합니다. **단순 URL 추가** 대화 상자에서 URL을 지정하고 **확인** 을 클릭하여 URL을 저장합니다. 새 URL을 활성 URL로 설정해야 할 경우 **이 URL을 선택한 도메인의 활성 URL로 설정합니다** 를 선택합니다. 변경 내용을 취소하려면 **취소** 를 클릭합니다.

다른 URL을 활성 URL(URL 옆에 녹색 확인 표시가 표시됨)로 설정하려면 URL을 선택하고 **활성화** 를 클릭합니다.

> [!NOTE]
> 각 SIP 도메인에 대해 하나의 활성 URL만 있을 수 있습니다.

URL을 제거해야 하는 경우 URL을 선택하고 **제거** 를 클릭합니다.

> [!CAUTION]
> 단순 URL 설정 대화 상자 페이지에 있는 정보를 신중하게 읽어 봅니다. 모임 URL을 제거하면 사용자가 예약한 모임에 액세스하지 못할 수 있습니다. 새 모임 URL을 활성 상태로 설정한 후에는 이전 URL을 그대로 남겨 두는 것을 고려해 봅니다. 사용자가 더 이상 이전 모임 URL을 사용하지 않는 것이 확실해지면 이전 모임 URL을 안전하게 제거할 수 있습니다.

관리 액세스 URL을 편집하거나 변경하려면 항목을 편집합니다.

속성 편집 페이지에서 모든 변경을 마쳤으면 **확인** 을 클릭하여 변경 내용을 저장합니다. 변경 내용을 취소하려면 **취소** 를 클릭합니다.

## <a name="central-management-server"></a>중앙 관리 서버

중앙 관리 서버는 정의된 한 프런트 엔드 풀에서 정의된 다른 프런트 엔드 풀로 변경할 수 있습니다. 중앙 관리 서버의 위치를 변경하려면 **중앙 관리 서버를 설치할 프런트 엔드 서버** 아래의 드롭다운 목록에서 프런트 엔드 풀을 선택합니다. 프런트 엔드 서버는 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 프런트 엔드 서버일 수 있습니다.

> [!IMPORTANT]
> 인프라에 대한 중앙 관리 저장소를 정의, 게시 및 배포한 후에는 외부 프로세스로 중앙 관리 저장소를 다른 프런트 엔드로 재배치하지 않고서는 중앙 관리 저장소의 위치를 변경할 수 없습니다.

중앙 관리 저장소를 이동하는 자세한 내용은 cmdlet 참조의 [Move-CsManagementServer를](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps) Windows PowerShell 참조합니다.

## <a name="see-also"></a>참고 항목

이러한 설정을 정의 및 구성하는 방법에 대한 자세한 내용은 [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)을 참조하십시오.


