---
title: Lync 2010 클라이언트 컴퓨터에서 개인 연락처 저장소 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: '요약: 레거시 클라이언트에서 사용하는 개인 연락처 저장소를 구성합니다.'
ms.openlocfilehash: 66ef1c3726ea020669894769b48b2313e1da2e0e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833938"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Lync 2010 클라이언트 컴퓨터에서 개인 연락처 저장소 구성
  
비즈니스용 Skype 서버 2015 및 Exchange Server 2016 또는 Exchange Server 2013을 통합하는 경우 클라이언트에서 사용하는 개인 연락처 저장소를 구성해야 합니다. 특히 Exchange를 개인 연락처 저장소로 사용하도록 비즈니스용 Skype를 구성하고 동시에 사용자가 해당 결정을 다시울 수 없는지 해야 합니다. 각 클라이언트 컴퓨터에서 레지스트리 값을 만들고 구성하면 됩니다.
  
> [!NOTE]
> 다음 절차는 Lync 2010 클라이언트를 사용하는 클라이언트에만 필요합니다. Lync 2013 클라이언트 및 모든 비즈니스용 Skype 클라이언트에는 연락처 저장소 설정을 다시우는 옵션이 없습니다.
  
단일 컴퓨터에서 이 값을 구성하려면 다음 절차를 완료합니다.
  
1. 클라이언트 컴퓨터에서 시작을  클릭한 다음 실행을 **클릭합니다.**
2. **실행** 대화 상자에 regedit를 입력한 다음 Enter 키를 누릅니다.
3. 레지스트리 편집기에서 HKEY_LOCAL_MACHINE 확장하고, **소프트웨어,** 정책을 확장하고,  **Microsoft를** 확장한 다음, **Communicator.**
4. 새 **Communicator** 마우스 오른쪽 단추로 클릭한 다음 **DWORD(32비트) 값을 클릭합니다.**
5. 새 값을 만든 후 PersonalContactStoreOverride를 입력한 다음 Enter를 눌러 값 이름을 다시 입력합니다.
6. PersonalContactStoreOverride의 값이 0으로 설정되어 있는지 확인한 다음 레지스트리 편집기를 닫습니다.

여러 컴퓨터에서 동일한 변경을 해야 하는 경우 사용자 지정 그룹 정책 개체를 만들어서 변경할 수 있습니다. Windows 10에서 이 작업을 수행하기 위한 자세한 내용은 그룹 정책 개체 만들기 [문서를 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
  
