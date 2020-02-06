---
title: 비즈니스용 Skype 서버에서 사용자에 게 보관 정책 적용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: '요약: 비즈니스용 Skype 서버에서 사용자에 게 보관 정책을 할당 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 7be62aaf5b2b70108cb67a36559b242377d26117
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819010"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 사용자에 게 보관 정책 적용

**요약:** 비즈니스용 Skype 서버에서 사용자에 게 보관 정책을 할당 하는 방법에 대해 알아봅니다.
  
비즈니스용 Skype Server에 속한 사용자에 대해 보관 하기 위해 하나 이상의 사용자 정책을 만든 경우 해당 사용자 또는 사용자 그룹에 적절 한 정책을 적용 하 여 특정 사용자에 대 한 보관 지원을 구현할 수 있습니다. 예를 들어 내부 통신 보관을 지원 하기 위한 정책을 만드는 경우 사용자의 비즈니스용 Skype 서버 통신 보관을 지원 하기 위해 하나 이상의 사용자 또는 사용자 그룹에 적용할 수 있습니다.
  
> [!NOTE]
> 배포에 Microsoft Exchange 통합을 사용 하도록 설정 하면 exchange 원본 위치 유지 정책에서 Exchange를 사용 하는 사용자에 대해 보관을 사용할 수 있는지 여부를 제어 하 고 사서함이 원본 위치 유지에 배치 되도록 합니다. 자세한 내용은 비즈니스용 [Skype 서버에서 보관 계획](../../plan-your-deployment/archiving/archiving.md) 및 비즈니스용 [skype 서버에 대 한 Exchange 저장소 통합 구성](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)을 참조 하세요. 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>제어판을 사용 하 여 사용자 정책 적용

제어판을 사용 하 여 사용자 정책을 적용 하려면 다음을 수행 합니다.
  
1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다. 
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 
    
3. 왼쪽 탐색 모음에서 **사용자**를 클릭 한 다음 구성 하려는 사용자 계정을 검색 합니다. 
    
4. 검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.
    
5. **보관 정책**에서 **Lync Server 사용자 편집** 에서 적용 하려는 보관 사용자 정책을 선택 합니다.
    
    > [!NOTE]
    > 자동 설정은 기본 서버 설치 설정을 적용 합니다. ** \<\> ** 이러한 설정은 서버에 의해 자동으로 적용됩니다.
  
6. **커밋**을 클릭합니다.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 사용자 정책 적용

Windows PowerShell **CsArchivingPolicy** cmdlet을 사용 하 여 사용자 정책을 적용할 수도 있습니다.
  
다음 명령을 사용 하 여 사용자 단위 보관 정책을 RedmondArchivingPolicy: 진구 Myer에 할당 합니다.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

이 명령은 등록자 풀 atl-cs-001.contoso.com에 속한 계정이 있는 모든 사용자에 대해 사용자별 보관 정책 RedmondArchivingPolicy를 할당 합니다. 이 명령에 사용 된 필터 매개 변수에 대 한 자세한 내용은 [Get CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet 설명서를 참조 하세요.
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

다음 명령을 사용 하 여 이전에: 진구 Myer에 할당 된 사용자 단위 보관 정책을 제거 합니다. 사용자별 정책이 제거 되 면: 진구 Myer는 글로벌 정책을 사용 하 여 자동으로 관리 되거나 (있는 경우) 로컬 사이트 정책이 됩니다. 사이트 정책이 전역 정책 보다 우선 합니다.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

자세한 내용은 [CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet 설명서를 참조 하세요.
  

