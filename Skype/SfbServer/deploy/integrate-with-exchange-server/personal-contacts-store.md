---
title: Lync 2010 클라이언트 컴퓨터에서 개인 연락처 저장소 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: '요약: 레거시 클라이언트에서 사용 하는 개인 연락처 저장소를 구성 합니다.'
ms.openlocfilehash: ba9cb7ee485f94162a642f8e877213a7bcd47c55
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188127"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Lync 2010 클라이언트 컴퓨터에서 개인 연락처 저장소 구성
  
비즈니스용 Skype 서버 2015 및 Exchange Server 2016 또는 Exchange Server 2013을 통합 하는 경우에는 클라이언트가 사용 하는 개인 연락처 저장소를 구성 해야 합니다. 특히, Exchange를 개인 연락처 저장소로 사용 하도록 비즈니스용 Skype를 구성 하 고, 동시에 사용자가 해당 결정을 재정의할 수 없도록 해야 합니다. 각 클라이언트 컴퓨터에서 레지스트리 값을 만들고 구성 하 여이 작업을 수행할 수 있습니다.
  
> [!NOTE]
> 다음 절차는 Lync 2010 클라이언트 또는 이전 버전을 사용 하는 클라이언트에만 필요 합니다. Lync 2013 클라이언트와 모든 비즈니스용 Skype 클라이언트에는 연락처 저장소 설정을 재정의 하는 옵션이 없습니다.
  
단일 컴퓨터에서이 값을 구성 하려면 다음 절차를 완료 합니다.
  
1. 클라이언트 컴퓨터에서 **시작** 을 클릭 한 다음 **실행**을 클릭 합니다.
2. **실행** 대화 상자에서 regedit를 입력 한 다음 enter 키를 누릅니다.
3. 레지스트리 편집기에서 **HKEY_LOCAL_MACHINE**을 확장 하 고, **소프트웨어**를 확장 하 고, **정책을**확장 하 고, **Microsoft**를 확장 한 다음, **Communicator**를 확장 합니다.
4. **Communicator**를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **DWORD (32 비트) 값**을 클릭 합니다.
5. 새 값을 만든 후 PersonalContactStoreOverride를 입력 하 고 enter 키를 눌러 값의 이름을 바꿉니다.
6. PersonalContactStoreOverride의 값이 0으로 설정 되어 있는지 확인 한 다음 레지스트리 편집기를 닫습니다.

여러 컴퓨터에서 동일 하 게 변경 해야 하는 경우 사용자 지정 그룹 정책 개체를 만들어이 작업을 수행할 수 있습니다. Windows 10에서이 작업을 수행 하는 방법에 대 한 자세한 내용은 [그룹 정책 개체 만들기](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) 문서를 참조 하세요.
  
