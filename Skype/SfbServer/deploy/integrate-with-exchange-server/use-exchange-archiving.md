---
title: 보관 비즈니스용 Skype 서버 사용하도록 Exchange Server 구성
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: '요약: Exchange Server 2016 또는 Exchange Server 2013 및 2013에 대한 IM 비즈니스용 Skype 서버.'
ms.openlocfilehash: 0b154c9184002cf663d61395277471f8a927c556
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840590"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>보관 비즈니스용 Skype 서버 사용하도록 Exchange Server 구성

**요약:** 2016 또는 Exchange Server 2013 및 Exchange Server IM 기록을 비즈니스용 Skype 서버.

비즈니스용 Skype 서버 데이터베이스가 아닌 사용자의 Exchange Server 2016 또는 Exchange Server 2013 사서함에 메신저 및 웹 회의 기록을 보관할 SQL Server 있습니다. 이 옵션을 사용하면 사용자의 사서함에 있는 제거 폴더에 기록이 기록됩니다. 제거 폴더는 복구 가능한 항목 폴더에 있는 숨겨진 폴더입니다. 이 폴더는 최종 사용자에게 표시되지는 않습니다. 이 폴더는 Exchange 검색 엔진에서 인덱싱하며 Exchange 사서함 검색 및/또는 Microsoft SharePoint Server 2013을 사용하여 검색할 수 있습니다. 전자 메일 및 기타 Exchange 통신 보관을 담당하는 Exchange In-Place 보류 기능에서 사용하는 동일한 폴더에 정보가 저장되어 있기 때문에 관리자는 단일 도구를 사용하여 사용자에 대해 보관된 모든 전자 통신을 검색할 수 있습니다.

> [!IMPORTANT]
> 대화 보관을 완전히 사용하지 않도록 설정하려면 대화 기록도 사용하지 않도록 설정해야 합니다. 자세한 내용은 다음 항목을 [참조하십시오. Managing the Archiving of internal and external communications in 비즈니스용 Skype 서버](/previous-versions/office/lync-server-2013/lync-server-2013-managing-the-archiving-of-internal-and-external-communications), [New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps)및 [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps).

기록을 보관할 수 Exchange Server 서버 간 인증을 먼저 구성해야 비즈니스용 Skype 서버 Exchange Server. 서버 대 서버 인증을 설정한 후 다음 작업을 비즈니스용 Skype 서버(설정 및 구성에 따라 이러한 작업을 모두 완료하지 않을 수도 있습니다).

1. 보관 Exchange 설정을 수정하여 비즈니스용 Skype 서버 보관을 사용하도록 설정할 수 있습니다. 이 단계는 모든 배포에 필요합니다.

2. 사용자의 내부 및/또는 외부 통신에 대해 보관을 사용하도록 설정 이 단계는 모든 배포에 필요합니다.

3. 각 사용자에 대해 ExchangeArchivingPolicy 속성을 구성합니다. 이 단계는 사용자 및 비즈니스용 Skype 서버 Exchange Server 포리스트에 있는 경우만 필요합니다.

## <a name="step-1-enabling-exchange-archiving"></a>1단계: 보관 Exchange 사용

비즈니스용 Skype 서버 보관은 주로 보관 구성 설정을 사용하여 관리됩니다. 설치 비즈니스용 Skype 서버 이러한 설정의 전역 컬렉션이 자동으로 하나만 부여됩니다. 관리자는 선택적으로 사이트 범위에서 보관 설정의 새 컬렉션을 만들 수 있습니다. 기본적으로 보관은 전역 설정에서 사용하도록 설정되지 않으며 이러한 설정에서 Exchange 사용하도록 설정되어 있지 않습니다. 보관 Exchange 사용하려면 관리자는 이러한 구성 설정에서 EnableArchiving 및 EnableExchangeArchiving 속성을 모두 구성해야 합니다. EnableArchiving 속성은 다음 세 가지 값 중 하나로 설정할 수 있습니다.

- **없음.** 보관을 사용할 수 없습니다. 이 값은 기본값입니다. EnableArchiving을 None으로 설정하면 모든 보관 데이터베이스 또는 비즈니스용 Skype 서버 보관 데이터베이스에 아무 것도 Exchange Server.

- **ImOnly**. 인스턴트 메시지 기록만 보관됩니다. 보관을 Exchange 경우 이러한 기록은 보관된 Exchange Server. 보관을 Exchange 사용하지 않도록 설정하면 이러한 기록이 보관된 비즈니스용 Skype 서버.

- **ImAndWebConf**. 인스턴트 메시지 기록과 웹 회의 기록이 모두 보관됩니다. 보관 Exchange 사용하도록 설정된 경우 이러한 기록은 해당 문서에 Exchange Server. 보관을 Exchange 사용하지 않도록 설정하면 이러한 기록이 보관된 비즈니스용 Skype 서버.

EnableExchangeArchiving 속성은 부울 값입니다. EnableExchangeArchiving을 True($True)로 설정하여 Exchange 보관을 사용하도록 설정하거나 EnableExchangeArchiving을 False($False)로 설정하여 Exchange 보관을 사용하지 않도록 설정할 수 있습니다. 예를 들어 다음 명령은 인스턴트 메시징 문자를 보관할 수 있도록 하여 보관을 Exchange 수 있습니다.

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Exchange 보관을 사용하지 않도록 설정하기 위해 다음과 같은 명령을 사용하면 인스턴트 메시징 보관을 사용할 수 있지만 Exchange 보관을 사용하지 않도록 설정할 수 있습니다(즉, 기록은 보관에 비즈니스용 Skype 서버).

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> EnableArchiving 속성을 None으로 설정하면 인스턴트 비즈니스용 Skype 서버 및 웹 회의 기록이 전혀 보관되지 않습니다. 이 경우 서버는 EnableExchangeArchiving에 대해 구성된 값을 무시합니다.

Exchange 보관을 사용하도록 설정하거나 사용하지 않도록 설정할 수도 비즈니스용 Skype 서버. 이렇게 하려면 다음 절차를 완료합니다.

1. 제어판에서 모니터링 및 보관을 클릭한 다음 보관 구성 **을 클릭합니다.**

2. 보관 **구성 탭에서** 수정할 보관 설정 컬렉션(예: **Global** 컬렉션)을 두 번 클릭합니다.

3. 보관  설정 편집 창에서 보관 설정  드롭다운 목록을 클릭하고 **메신저** 세션 보관(인스턴트 메시징 세션만 보관) 또는 **메신저** 및 웹 회의 세션 보관(인스턴트 메시징 및 웹 회의 세션 모두 보관)을 선택합니다.

4. 보관할 항목을 선택한 후 Exchange Server  통합 확인란을 선택하여 보관을 사용하도록 Exchange 합니다. 보관을 사용하지 Exchange 확인란의 선택을 취소합니다.

> [!NOTE]
> 보관 **Exchange Server** 사용 안 함을 로 설정한 경우 통합 확인란을 사용할 **수 없습니다.**  먼저 보관을 사용하도록 설정한 다음 보관을 사용하도록 Exchange 합니다.

비즈니스용 Skype 서버 Exchange Server 포리스트에 있는 경우 개별 사용자에 대한 보관(또는 전자 메일 계정이 Exchange Server 이상인 사용자)에 대한 보관은 Exchange In-Place 보류 정책을 사용하여 관리됩니다. 이전 버전의 Exchange 있는 사용자가 있는 경우 해당 사용자에 대한 보관은 비즈니스용 Skype 서버 사용하여 관리됩니다. Exchange Server 2016 또는 Exchange Server 2013에 계정이 있는 사용자만 자신의 비즈니스용 Skype 기록을 보관할 Exchange.

비즈니스용 Skype 서버 및 Exchange Server 포리스트에 있는 경우 개별 사용자 계정에 대해 ExchangeArchivingPolicy 속성을 구성하여 개별 사용자에 대한 보관을 관리합니다. 자세한 내용은 3단계를 참조하세요.

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>2단계: 내부 및/또는 외부 통신 보관 사용

보관 및 보관을 사용하도록 설정한 Exchange 사용자 세션이 실제로 보관되도록 적절한 보관 정책을 수정해야 합니다. 단순히 보관을 사용하도록 설정(1단계)을 해서 인스턴트 메시징 및 웹 비즈니스용 Skype 서버 기록 보관을 시작하지는 않습니다. 대신 보관 정책을 사용하여 내부 및/또는 외부 보관을 사용하도록 설정해야 합니다. 설치하는 비즈니스용 Skype 서버 두 속성을 포함하는 단일 전역 보관 정책도 설치합니다.

- **ArchiveInternal**. True($True)로 설정하면 조직에 Active Directory 계정이 있는 사용자만 포함하는 내부 통신 세션이 보관됩니다.

- **ArchiveExternal**. True($True)로 설정하면 내부 통신 세션(조직에 Active Directory 계정이 없는 사용자 한 명 이상이 관련된 세션)이 보관됩니다.

기본적으로 이러한 속성 값은 모두 False로 설정되어 있습니다. 즉, 내부 및 외부 통신 세션은 모두 보관되지 않습니다. 전역 정책을 수정하려면 비즈니스용 Skype 서버 관리 셸 및 Set-CsArchivingPolicy 수 있습니다. 이 명령은 내부 및 외부 통신 세션 모두의 보관을 활성화합니다.

```powershell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

또는 사이트 범위 또는 사용자 New-CsArchivingPolicy 새 정책을 만들 수 있습니다. 예를 들어 다음 명령은 RedmondArchivingPolicy라는 새 사용자당 보관 정책을 만듭니다.

```powershell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

사용자당 정책을 만드는 경우 해당 정책을 적절한 사용자에게 할당해야 합니다. 예를 들면 다음과 같습니다.

```powershell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

보관 정책은 제어판을 사용하여 관리할 비즈니스용 Skype 서버 있습니다. 제어판 내에서 모니터링 및 보관을 **클릭한** 다음 보관 **정책을 클릭합니다.** 기존 정책을 수정하려면 정책(예: 전역)을 두 번 클릭한 다음 보관 정책 편집 창에서 필요한  경우 내부 통신  보관 및 외부 통신 보관 확인란을 선택하거나 선택을 취소합니다.  새 보관 정책을 만들려면 새로 만들기를 클릭한  **다음** 사이트 정책 또는 사용자 정책을 **선택합니다.** 새 사용자 정책을 만드는 경우 사용자 탭에서 적절한 사용자  계정에 액세스하고 해당 사용자에게 새 정책을 할당해야 합니다.

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>3단계: ExchangeArchivingPolicy 속성 구성

사용자 비즈니스용 Skype 서버 Exchange Server 포리스트에 있는 경우 보관 구성 설정에서 Exchange 보관을 사용하도록 설정하는 것만으로는 충분하지 않습니다. 이 경우 인스턴트 메시징 및 웹 회의 기록이 저장되지 Exchange. 대신 각 사용자 계정과 관련된 각 사용자 계정에 대해 ExchangeArchivingPolicy 속성을 비즈니스용 Skype 서버 합니다. 이 속성은 다음 네 가지 값 중 하나로 설정할 수 있습니다.

1. **Uninitialized**. 보관은 사용자의 In-Place 사서함에 대해 구성된 보류 Exchange 나타냅니다. In-Place 사서함에서 보류를 사용하도록 설정하지 않은 경우 사용자는 자신의 메시징 및 웹 회의 기록을 해당 사서함에 비즈니스용 Skype 서버.

2. **UseLyncArchivingPolicy**. 사용자의 인스턴트 메시징 및 웹 회의 기록은 사용자의 인스턴트 메시징이 아닌 비즈니스용 Skype 서버 보관해야 Exchange.

3. **NoArchiving**. 사용자의 인스턴트 메시징 및 웹 회의 기록을 보관하지 말아야 한다고 나타냅니다. 이 설정은 사용자에게 할당된 비즈니스용 Skype 서버 모든 보관 정책을 다시 지정합니다.

4. **ArchivingToExchange**. 사용자의 사서함에 할당되거나 할당되지 않은 보류 Exchange 보류 설정에 관계없이 사용자의 인스턴트 메시징 및 웹 회의 기록을 In-Place 보관해야 한다고 나타냅니다.

예를 들어 인스턴트 메시징 및 웹 회의 기록을 항상 보관하도록 사용자 계정을 구성하려면 Exchange 관리 셸에서 다음과 같은 명령을 비즈니스용 Skype 서버 있습니다.

```powershell
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

사용자 그룹에 대해 동일한 보관 정책을 설정하려는 경우(예: 지정된 등록자 풀에 있는 모든 사용자) 다음과 같은 명령을 사용할 수 있습니다.

```powershell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

ExchangeArchivingPolicy 속성의 값을 구성하려면 비즈니스용 Skype 서버 및 Windows PowerShell 관리 셸을 사용해야 합니다. 이 속성은 조직의 관리자에게는 비즈니스용 Skype 서버.

특정 보관 정책이 할당된 모든 사용자의 목록을 보시고자 하는 경우 ExchangeArchivingPolicy 속성이 Uninitialized로 설정된 모든 사용자의 Active Directory 표시 이름을 반환하는 다음과 같은 명령을 사용할 수 있습니다.

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

마찬가지로 이 명령은 ExchangeArchivingPolicy 속성이 UseLyncArchivingPolicy로 설정되지 않은 사용자의 표시 이름을 반환합니다.

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```