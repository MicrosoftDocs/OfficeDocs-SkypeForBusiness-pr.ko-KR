---
title: Exchange Server 아카이빙 사용을 위해 비즈니스용 Skype 서버 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: '요약: Exchange Server 2016 또는 Exchange Server 2013 및 비즈니스용 Skype Server에 대 한 IM 성적 증명서를 구성 합니다.'
ms.openlocfilehash: b24353a9742a48b35e21ac00df40a04fa60e444b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188115"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>Exchange Server 아카이빙 사용을 위해 비즈니스용 Skype 서버 구성

**요약:** Exchange Server 2016 또는 Exchange Server 2013 및 비즈니스용 Skype Server에 대 한 IM 기록 구성

비즈니스용 Skype Server는 관리자에 게 SQL Server 데이터베이스가 아닌 사용자의 Exchange Server 2016 또는 Exchange Server 2013 사서함에 인스턴트 메시지 및 웹 회의 성적 증명서를 보관 하는 옵션을 제공 합니다. 이 옵션을 사용 하도록 설정 하면 사용자의 사서함에 있는 제거 폴더에 대 한 증명서가 기록 됩니다. 제거 폴더는 복구 가능한 항목 폴더에 있는 숨겨진 폴더입니다. 이 폴더는 최종 사용자에 게 표시 되지 않지만,이 폴더는 Exchange 검색 엔진을 기준으로 색인화 되며 Exchange 사서함 검색 및/또는 Microsoft SharePoint Server 2013를 사용 하 여 검색할 수 있습니다. 정보는 Exchange 원본 위치 유지 기능 (전자 메일 보관 및 기타 Exchange 통신을 담당 하는 경우)에서 사용 하는 동일한 폴더에 저장 되므로, 관리자는 단일 도구를 사용 하 여 다음에 보관 된 모든 전자 통신을 검색할 수 있습니다. 클릭할.

> [!IMPORTANT]
> 대화 보관을 완전히 사용 하지 않으려면 대화 내역도 사용 하지 않도록 설정 해야 합니다. 자세한 내용은 비즈니스용 Skype 서버, [새로운 csclientpolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)및 [Set csclientpolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)의 [내부 및 외부 통신 보관 관리](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx)항목을 참조 하세요.

Exchange Server에 성적 보관용을 보관 하려면 비즈니스용 Skype 서버와 Exchange Server 간에 서버 간 인증을 구성 하는 것으로 시작 해야 합니다. 서버 간 인증이 적용 된 후에는 비즈니스용 Skype 서버에서 다음 작업을 수행할 수 있습니다 (설정 및 구성에 따라 이러한 작업을 모두 완료 하지 않아도 됨).

1. 비즈니스용 Skype Server 보관 구성 설정을 수정 하 여 Exchange 보관을 사용 하도록 설정 합니다. 모든 배포에이 단계가 필요 합니다.

2. 사용자에 대 한 내부 및/또는 외부 통신을 보관할 수 있습니다. 모든 배포에이 단계가 필요 합니다.

3. 각 사용자에 대 한 ExchangeArchivingPolicy 속성을 구성 합니다. 이 단계는 비즈니스용 Skype 서버와 Exchange Server가 서로 다른 포리스트에 있는 경우에만 필요 합니다.

## <a name="step-1-enabling-exchange-archiving"></a>1 단계: Exchange 보관 기능 설정

비즈니스용 Skype Server의 보관은 기본적으로 보관 구성 설정을 사용 하 여 관리 됩니다. 비즈니스용 Skype 서버를 설치 하면 이러한 설정의 단일 전역 컬렉션이 자동으로 지정 됩니다. (관리자가 사이트 범위에서 선택적으로 새 보관 설정 모음을 만들 수 있습니다.) 기본적으로, 전역 설정에서는 보관을 사용할 수 없으며, 이러한 설정에서는 Exchange 보관도 사용할 수 없습니다. Exchange 보관을 사용 하기 위해 관리자는 이러한 구성 설정에서 EnableArchiving 및 EnableExchangeArchiving 속성을 모두 구성 해야 합니다. EnableArchiving 속성은 다음 세 가지 가능한 값 중 하나로 설정할 수 있습니다.

- **없음**. 보관을 사용할 수 없습니다. 기본값입니다. EnableArchiving이 없음으로 설정 된 경우 비즈니스용 Skype Server 보관 데이터베이스 또는 Exchange Server에는 아무 것도 보관 되지 않습니다.

- **Imonly**. 인스턴트 메시지 증명서만 보관 됩니다. Exchange 보관을 사용 하는 경우 이러한 증명서는 Exchange Server에 보관 됩니다. Exchange 보관을 사용 하지 않도록 설정 하면 이러한 증명서는 비즈니스용 Skype 서버에 보관 됩니다.

- **Imandwebconf**. 인스턴트 메시지 기록 및 웹 회의 기록 모두 보관 됩니다. Exchange 보관을 사용 하는 경우 이러한 증명서는 Exchange Server에 보관 됩니다. Exchange 보관을 사용 하지 않도록 설정 하면 이러한 증명서는 비즈니스용 Skype 서버에 보관 됩니다.

EnableExchangeArchiving 속성은 부울 값입니다. Exchange 보관을 사용 하도록 EnableExchangeArchiving ($True) 설정 하거나 EnableExchangeArchiving에서 False ($False)로 설정 하 여 Exchange 보관을 사용 하지 않도록 합니다. 예를 들어이 명령을 사용 하 여 메신저 대화를 보관 하 고 Exchange 보관을 사용할 수도 있습니다.

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Exchange 보관을 사용 하지 않도록 설정 하려면 다음과 같은 명령을 사용 합니다 (인스턴트 메시징 보관을 사용할 수 있지만 Exchange로 보관할 수 없음) (즉, 출장을 비즈니스용 Skype 서버에 보관 됨):

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> EnableArchiving 속성이 없음으로 설정 된 경우 비즈니스용 Skype 서버는 인스턴트 메시지와 웹 회의 성적 증명서를 전혀 보관 하지 않습니다. 이 경우 서버는 EnableExchangeArchiving에 대해 구성 된 값만 무시 합니다.

비즈니스용 Skype 서버를 사용 하 여 Exchange 보관을 사용 하거나 사용 하지 않도록 설정할 수도 있습니다. 이렇게 하려면 다음 절차를 수행 합니다.

1. 제어판에서 **모니터링 및 보관**을 클릭 한 다음 **구성을 보관**을 클릭 합니다.

2. **보관 구성** 탭에서 수정할 보관 설정 모음 (예: **전역** 컬렉션)을 두 번 클릭 합니다.

3. **보관 설정 편집** 창에서 **보관 설정** 드롭다운 목록을 클릭 하 고 **im 세션 보관** (인스턴트 메시징 세션만 보관) 또는 **im 및 웹 회의 세션 보관** 을 선택 합니다 (둘 다 보관 가능). 인스턴트 메시지 및 웹 회의 세션).

4. 보관할 항목을 선택한 후 exchange **Server 통합** 확인란을 선택 하 여 exchange 보관을 사용 하도록 설정 합니다. Exchange 보관을 사용 하지 않도록 설정 하려면이 확인란의 선택을 취소 합니다.

> [!NOTE]
> 보관 **설정이** **보관을 사용 하지 않도록**설정 되어 있는 경우 **Exchange Server 통합** 확인란을 사용할 수 없습니다. 보관을 먼저 설정한 다음 Exchange 보관을 사용 하도록 설정 해야 합니다.

비즈니스용 Skype Server 및 Exchange Server가 동일한 포리스트에 있는 경우, 개별 사용자 (또는 Exchange Server에 전자 메일 계정이 있는 사용자에 대 한 보관)는 Exchange 원본 위치 유지 정책을 사용 하 여 관리 됩니다. 이전 버전의 Exchange에서 거주 하는 사용자가 있는 경우, 해당 사용자에 대 한 보관은 비즈니스용 Skype 서버 보관 정책을 사용 하 여 관리 됩니다. Exchange Server 2016 또는 Exchange Server 2013에 계정이 있는 사용자만 Exchange에 비즈니스용 Skype 성적 증명서를 보관할 수 있습니다.

비즈니스용 Skype 서버와 Exchange Server가 서로 다른 포리스트에 있는 경우 개별 사용자 계정에 대해 ExchangeArchivingPolicy 속성을 구성 하 여 개인 사용자의 보관을 관리 합니다. 자세한 내용은 3 단계를 참조 하세요.

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>2 단계: 내부 및/또는 외부 통신의 아카이빙 사용

보관 (및 Exchange 보관)을 사용 하도록 설정한 후에는 사용자 세션이 실제로 보관 되도록 적절 한 보관 정책을 수정 해야 합니다. 간단 하 게 보관 (1 단계)을 사용 하도록 설정 하면 비즈니스용 Skype 서버에서 인스턴트 메시지 및 웹 회의 내용 보관을 시작 하는 것이 발생 하지 않습니다. 대신 보관 정책을 사용 하 여 내부 및/또는 외부 보관을 사용 하도록 설정 해야 합니다. 비즈니스용 Skype Server를 설치할 때 다음과 같은 두 가지 속성을 포함 하는 하나의 전역 보관 정책만 설치 하면 됩니다.

- **ArchiveInternal**. True ($True)로 설정 하는 경우 조직에서 Active Directory 계정이 있는 사용자만 포함 하는 내부 통신 세션을 보관 하는 것을 나타냅니다.

- **ArchiveExternal**. True ($True)로 설정 되 면 내부 통신 세션 (조직에서 Active Directory 계정이 없는 사용자가 하나 이상 포함 된 세션)이 보관 됨을 나타냅니다.

기본적으로 이러한 속성 값은 모두 False로 설정 되며,이는 내부 및 외부 통신 세션도 보관 되지 않는다는 의미입니다. 전역 정책을 수정 하려면 비즈니스용 Skype 서버 관리 셸 및 CsArchivingPolicy cmdlet을 사용 하면 됩니다. 이 명령을 사용 하 여 내부 및 외부 통신 세션을 모두 보관할 수 있습니다.

```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

또는 New-CsArchivingPolicy를 사용 하 여 사이트 범위 또는 사용자 단위 범위에서 새 정책을 만들 수 있습니다. 예를 들어이 명령은 RedmondArchivingPolicy 이라는 새 사용자별 보관 정책을 만듭니다.

```
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

사용자별 정책을 만든 경우 해당 사용자에 게 해당 정책을 할당 해야 합니다. 예를 들면 다음과 같습니다.

```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

비즈니스용 Skype Server 제어판을 사용 하 여 보관 정책을 관리할 수도 있습니다. 제어판에서 **모니터링 및 보관** 을 클릭 한 다음 **보관 정책을**클릭 합니다. 기존 정책을 수정 하려면 정책을 두 번 클릭 하 고 (예: 전역) **보관 정책 편집** 창에서 **내부 통신 보관** 및 **외부 통신 보관** 확인란을 필요에 따라 선택 하거나 선택을 취소 합니다. 새 보관 정책을 만들려면 **새로 만들기** 를 클릭 한 다음 **사이트 정책** 또는 **사용자 정책을**선택 합니다. 새 사용자 정책을 만드는 경우 **사용자** 탭에서 해당 사용자 계정에 액세스 하 여 새 정책을 해당 사용자에 게 할당 해야 합니다.

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>3 단계: ExchangeArchivingPolicy 속성 구성

비즈니스용 Skype 서버와 Exchange Server가 서로 다른 포리스트에 있는 경우, 보관 구성 설정에서 단순히 Exchange 보관을 사용 하도록 설정 하는 것 만으로는 충분 하지 않습니다. 이로 인해 인스턴트 메시지와 웹 회의에 대 한 증명서는 Exchange에 보관 되지 않습니다. 대신, 관련 된 각 비즈니스용 Skype Server 사용자 계정에서 ExchangeArchivingPolicy 속성을 구성 해야 합니다. 이 속성은 다음 네 가지 가능한 값 중 하나로 설정할 수 있습니다.

1. **초기화 되지 않았습니다**. 보관이 사용자의 Exchange 사서함에 대해 구성 된 원본 위치 유지 설정을 기반으로 함을 나타냅니다. 사용자의 사서함에 원본 위치 유지가 사용 하도록 설정 되어 있지 않으면 사용자는 비즈니스용 Skype 서버에 메시징 및 웹 회의 성적 증명서를 보관 합니다.

2. **UseLyncArchivingPolicy**. 사용자의 인스턴트 메시지 및 웹 회의 내용 작성을 Exchange가 아닌 비즈니스용 Skype 서버에 보관 해야 함을 나타냅니다.

3. **Noarchiving**. 사용자의 인스턴트 메시지 및 웹 회의 내용에 대 한 보관이 금지 됨을 나타냅니다. 이 설정은 사용자에 게 할당 된 모든 비즈니스용 Skype 서버 보관 정책 보다 우선 합니다.

4. **ArchivingToExchange**. 사용자의 사서함에 할당 되지 않은 원본 위치 유지 설정에 관계 없이 사용자의 인스턴트 메시지 및 웹 회의 기록에 대해 Exchange에 보관 해야 함을 나타냅니다.

예를 들어 인스턴트 메시지 및 웹 회의 기록 내용이 항상 Exchange에 보관 되도록 사용자 계정을 구성 하려면 비즈니스용 Skype 서버 관리 셸에서와 유사한 명령을 사용할 수 있습니다.

```
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

사용자 그룹에 대해 동일한 보관 정책을 설정 하려는 경우 (예: 지정 된 등록자 풀에 속한 모든 사용자) 다음과 같은 명령을 사용할 수 있습니다.

```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

ExchangeArchivingPolicy 속성의 값을 구성 하려면 비즈니스용 Skype 서버 관리 셸 (및 Windows PowerShell)을 사용 해야 한다는 점에 유의 하세요. 이 속성은 비즈니스용 Skype 서버의 관리자에 게 노출 되지 않습니다.

특정 보관 정책을 할당 한 모든 사용자의 목록을 보려면 ExchangeArchivingPolicy 속성을 설정한 모든 사용자의 Active Directory 표시 이름을 반환 하는 다음과 유사한 명령을 사용할 수 있습니다... 초기화 되지 않음:

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

마찬가지로이 명령은 ExchangeArchivingPolicy 속성이 UseLyncArchivingPolicy로 설정 되지 않은 사용자의 표시 이름을 반환 합니다.

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```


