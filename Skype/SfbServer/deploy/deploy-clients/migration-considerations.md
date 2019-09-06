---
title: Skype 실 시스템 마이그레이션 고려 사항
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: 이 항목에서는 비즈니스용 Skype Server 및 Lync Server의 여러 버전이 있는 환경에서 Skype 대화방 시스템을 배포 하는 방법에 대해 자세히 알아보세요.
ms.openlocfilehash: 6524a7312644ec306185b952caf17818d29344af
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774676"
---
# <a name="skype-room-system-migration-considerations"></a>Skype 실 시스템 마이그레이션 고려 사항
 
이 항목에서는 비즈니스용 Skype Server 및 Lync Server의 여러 버전이 있는 환경에서 Skype 대화방 시스템을 배포 하는 방법에 대해 자세히 알아보세요.
  
## <a name="migration-considerations"></a>마이그레이션 고려 사항

이 섹션에서는 다른 버전의 비즈니스용 Skype Server 또는 Lync Server를 포함 하는 다중 풀 환경에서 Skype 대화방 시스템을 배포 하는 경우에 대 한 지침을 제공 합니다. 
  
Lync 서버의 사용자 복제기 (UR) 구성 요소는 Active Directory에서 사용자 개체를 가져와 Lync Server 백 엔드 SQL Server 데이터베이스에 배치 합니다. Lync Server 2013의 UR만은 Skype 대화방 시스템 개체를 인식 합니다. 이전 버전의 Lync Server 및 Office 통신 서버는 LRS 개체를 지정 하는 Active Directory 특성을 검색 하지 않으므로이를 인식 하지 못합니다. 
  
Skype 채팅방 시스템 계정에서 Lync에 로그인 하 고 SRV 레코드 또는 DNS 레코드를 기준으로 자동 검색을 수행 하는 경우, 해당 계정이 Lync Server 또는 Office Communications Server의 이전 버전을 가리키는 경우 LRS에서 404을 찾을 수 없음 응답을 수신 합니다.  레거시 풀입니다. 레거시 풀은 Skype 대화방 시스템을 해당 Lync Server 2013 홈 풀로 리디렉션할 수 없게 됩니다. 
  
다음 옵션을 사용 하 여이 문제를 해결할 수 있습니다. 
  
- 자동 검색 SRV 레코드 (_sipinternaltls. _tcp)를 Lync Server 2013 풀에 가리킵니다.
    
- 첫 번째 옵션을 사용할 수 없는 경우 수동으로 LRS를 구성 하 고 Skype 대화방 시스템 콘솔 응용 프로그램에서 직접 구성 하 여 Lync Server 2013 풀 주소를 제공 해야 합니다. 
    
- Skype Room 시스템을 회사 네트워크 외부에 배포 하 고 Lync Edge 서버를 배포 하 여 레거시 풀이나 디렉터를 가리키도록 구성한 경우에는 Lync Server 2013 풀을 가리키는 보조 Edge 서버 사이트가 필요 합니다. 보조 Edge 서버 배포에 대 한 자세한 내용은 Edge 서버 배포 설명서를 참조 하세요. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Lync Server 2010 풀과 Skype 대화방 시스템의 상호 운용성

마이그레이션 중에 Lync Server 2010 풀에 있는 사용자가 모임을 예약 하 고 Skype 대화방 시스템 계정을 초대 하는 경우, 모임에 참석 하는 동안 Skype 대화방 시스템 클라이언트의 기능이 제한 됩니다. 
  
Skype 대화방 시스템 클라이언트가 Lync Server 2010에서 사용자가 구성한 예약 된 컨퍼런스 통화에 참가 하는 경우, Skype 대화방 시스템에는 다음과 같은 모임 시간 제한이 있습니다. 
  
- Skype 채팅방 시스템에서 다중 보기 비디오 갤러리를 표시할 수 없습니다.
    
- Skype 대화방 시스템 클라이언트가 발표자 인 경우 참가자에 대해 비디오 잠금을 적용할 수 없습니다.
    
- 다음과 같은 이유로 인해 Skype 대화방 시스템은 Lync Server 2013 회의 정책에서 허용 하는 경우에도 1080p 비디오 해상도 (인바운드 또는 아웃 바운드)를 표시할 수 없습니다. 
    
  - Lync Server 2010는 1080p resolution을 지원 하지 않습니다.
    
  - Skype 채팅방 시스템은 비디오 해상도에 대 한 이끌이 회의 정책에 의해 항상 제한 됩니다. 따라서 Lync 2010 풀에서 720p 해상도를 지원 하더라도, 이끌이 정책에서 지원 하지 않는 한, Skype 채팅방 시스템은 720p 해상도를 이용할 수 없습니다. 
    
- Lync 2013 클라이언트는 회의실에서 LRS 현재 상태를 감지 하 고 실제 회의실에 에코를 방지 하기 위해 자동으로 음소거 합니다. Lync Server 2010에서 호스팅하는 모임에서는이 기능이 작동 하지 않습니다.
    
- Lync Server 2010에서 호스트 되는 모임에 대 한 데스크톱 공유 성능에는 제한이 있습니다.
    
- 사용자는 Skype 대화방 시스템을 사용 하 여 Lync 2010에서 호스팅되는 개인 (제한 된) 모임에 참가할 수 없게 됩니다.
    

