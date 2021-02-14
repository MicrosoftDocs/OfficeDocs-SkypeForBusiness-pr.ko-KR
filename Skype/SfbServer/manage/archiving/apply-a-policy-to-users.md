---
title: 비즈니스용 Skype 서버에서 사용자에게 보관 정책 적용
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: '요약: 비즈니스용 Skype 서버에서 사용자에게 보관 정책을 할당하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 8dc74fcc8befe39b424b89c77aebca683fe17586
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817768"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 사용자에게 보관 정책 적용

**요약:** 비즈니스용 Skype 서버에서 사용자에게 보관 정책을 할당하는 방법에 대해 자세히 알아보습니다.
  
비즈니스용 Skype 서버에 있는 사용자에 대한 보관에 대한 사용자 정책을 하나 이상 만든 경우 해당 사용자 또는 사용자 그룹에 적절한 정책을 적용하여 특정 사용자에 대한 보관 지원을 구현할 수 있습니다. 예를 들어 내부 통신 보관을 지원하는 정책을 만드는 경우 하나 이상의 사용자 또는 사용자 그룹에 정책을 적용하여 사용자의 비즈니스용 Skype 서버 통신 보관을 지원할 수 있습니다.
  
> [!NOTE]
> 배포에 Microsoft Exchange 통합을 사용하도록 설정한 경우 Exchange In-Place 보류 정책은 Exchange에 있는 사용자에 대해 보관을 사용할 수 있는지 여부를 제어하고 사서함을 보류로 In-Place 제어합니다. 자세한 내용은 비즈니스용 Skype 서버에서 보관 계획 및 비즈니스용 [Skype](../../plan-your-deployment/archiving/archiving.md) 서버용 Exchange 저장소와의 통합 [구성을 참조하세요.](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md) 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>제어판을 사용하여 사용자 정책 적용

제어판을 사용하여 사용자 정책을 적용합니다.
  
1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다. 
    
2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다. 
    
3. 왼쪽 탐색 모음에서 **사용자** 를 클릭하고 구성하려는 사용자 계정을 검색합니다. 
    
4. 검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.
    
5. 보관 **정책에서 Lync Server 사용자** 편집에서 적용할 보관 사용자 정책을 선택합니다. 
    
    > [!NOTE]
    > 이 **\<Automatic\>** 설정은 기본 서버 설치 설정을 적용합니다. 이러한 설정은 서버에 의해 자동으로 적용됩니다.
  
6. **커밋** 을 클릭합니다.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>사용자 정책을 사용하여 Windows PowerShell

**Grant-CsArchivingPolicy** cmdlet을 사용하여 Windows PowerShell 정책을 적용할 수도 있습니다.
  
다음 명령은 사용자별 보관 정책 RedmondArchivingPolicy를 Ken Myer라는 사용자에게 지정합니다.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

이 명령은 등록자 풀에 있는 계정이 있는 모든 사용자에게 사용자당 보관 정책 RedmondArchivingPolicy를 atl-cs-001.contoso.com. 이 명령에 사용되는 Filter 매개 변수에 대한 자세한 내용은 [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet 설명서를 참조하십시오.
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

다음 명령은 이전에 Ken Myer에게 할당된 사용자당 보관 정책을 제거합니다. 사용자당 정책이 제거된 후 Ken Myer는 자동으로 글로벌 정책 또는 로컬 사이트 정책(있는 경우)을 사용하여 관리됩니다. 사이트 정책은 글로벌 정책보다 우선 적용됩니다.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

자세한 내용은 [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet 설명서를 참조하십시오.
  

