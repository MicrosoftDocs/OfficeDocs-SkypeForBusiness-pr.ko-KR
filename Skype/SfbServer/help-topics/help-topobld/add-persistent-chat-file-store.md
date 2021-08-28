---
title: 영구 채팅 파일 저장소 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Standard Edition 서버 또는 Enterprise Edition 프런트 엔드 풀에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 기존 파일 공유를 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.
ms.openlocfilehash: 17ef0ff681b3a583c9423c5ea693f88b35db904d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615744"
---
# <a name="add-persistent-chat-file-store"></a>영구 채팅 파일 저장소 추가
 
Standard Edition 서버 또는 Enterprise Edition 프런트 엔드 풀에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 기존 파일 공유를 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.
  
> [!IMPORTANT]
> 비즈니스용 Skype 서버 공유는 Enterprise Edition 프런트 엔드 서버에는 찾을 수 없지만 Standard Edition 있습니다. 
  
> [!IMPORTANT]
> 파일 공유를 만들기 전에 토폴로지 작성기에서 파일 공유를 정의할 수 있지만 토폴로지를 게시하기 전에 정의한, 정의된 위치에 파일 공유를 만들어야 합니다. 
  
> [!IMPORTANT]
> 영구 채팅 서버 또는 영구 채팅 서버 풀을 토폴로지에 추가할 때 토폴로지 작성기에서 파일 저장소를 설정하고 파일 저장소에 사용할 파일 공유에 대해 DACL(사용자별 액세스 제어 목록)을 구성할 수 있어야 합니다. 이렇게 하려면 토폴로지 작성기를 실행하여 새 토폴로지를 게시할 때 파일 공유에 대한 모든 권한(읽기/쓰기/수정)을 가진 계정으로 로그온해야 합니다. 
  
## <a name="see-also"></a>참고 항목

[2015년 비즈니스용 Skype 서버 영구 채팅 서버 계획](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[2015 토폴로지에서 영구 채팅 비즈니스용 Skype 서버 추가](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[영구 채팅 서버에 대한 하드웨어 및 소프트웨어 요구 사항 비즈니스용 Skype 서버 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[비즈니스용 Skype 서버 서버 요구 사항](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[2015년 비즈니스용 Skype 서버 토폴로지 기본](../../plan-your-deployment/topology-basics/topology-basics.md)
