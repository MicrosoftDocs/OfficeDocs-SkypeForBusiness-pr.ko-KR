---
title: Skype 시스템 마이그레이션 고려 사항
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: 이 항목을 통해 여러 버전의 Skype 및 Lync Server가 있는 환경에 비즈니스용 Skype 서버 방법에 대해 자세히 알아보습니다.
---

# <a name="skype-room-system-migration-considerations"></a>Skype 시스템 마이그레이션 고려 사항
 
이 항목을 통해 여러 버전의 Skype 및 Lync Server가 있는 환경에 비즈니스용 Skype 서버 방법에 대해 자세히 알아보습니다.
  
## <a name="migration-considerations"></a>마이그레이션 고려 사항

이 섹션에서는 서로 다른 버전의 Skype 또는 Lync Server를 포함하는 다중 풀 환경에서 비즈니스용 Skype 서버 배포하는 경우 지침을 제공합니다. 
  
Lync Server의 UR(User Replicator) 구성 요소는 Active Directory에서 사용자 개체를 사용하여 Lync Server 백 엔드 데이터베이스로 SQL Server 합니다. Lync Server 2013의 UR만이 Room System Skype 인식합니다. 이전 버전의 Lync Server 및 Office Communications Server의 UR는 LRS 개체를 지정하는 Active Directory 특성을 검색하지 못하므로 이를 인식하지 못합니다. 
  
Skype 대화방 시스템 계정이 Lync에 로그인을 시도하고 SRV 레코드 또는 DNS A 레코드를 기반으로 자동 검색을 수행하고 해당 계정이 이전 버전의 Lync Server 또는 Office Communications Server를 사용하는 경우 LRS는 레거시 풀에서 404 찾을 수 없습니다 응답을 받게 됩니다. 레거시 풀은 룸 시스템을 Skype Lync Server 2013 홈 풀로 리디렉션할 수 없습니다. 
  
다음 옵션을 사용하여 이 문제를 해결할 수 있습니다. 
  
- 자동 검색 SRV 레코드(_sipinternaltls._tcp.contoso.com)를 Lync Server 2013 풀을 지정합니다.
    
- 첫 번째 옵션을 사용할 수 없는 경우 LRS를 수동으로 구성하고 Skype 룸 시스템 콘솔 응용 프로그램에서 직접 구성하여 Lync Server 2013 풀 주소를 제공해야 합니다. 
    
- Skype 네트워크 외부에 배치된 경우 Lync 에지 서버가 배포되고 레거시 풀 또는 감독을 사용하도록 구성된 경우 보조 에지 서버 사이트가 필요합니다. 이 사이트는 Lync Server 2013 풀을 지점으로 합니다. 보조 에지 서버 배포에 대한 자세한 내용은 에지 서버 배포 설명서를 참조하십시오. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Skype Lync Server 2010 풀과의 룸 시스템 상호 운영성

마이그레이션 중에 Lync Server 2010 풀에 있는 사용자가 모임을 예약하고 Skype 회의실 시스템 계정을 초대하는 경우 Skype 회의실 시스템 클라이언트는 모임에 참석하는 동안 제한된 기능을 하게 됩니다. 
  
Skype 회의실 시스템 클라이언트가 Lync Server 2010에 있는 사용자가 구성한 예약된 전화 회의에 참가하면 Skype 회의실 시스템에 다음과 같은 모임 내 제한이 있습니다. 
  
- Skype 다중 보기 비디오 갤러리를 표시하지 못합니다.
    
- 이 Skype 클라이언트가 발표자인 경우 참가자에게 비디오 잠금을 적용할 수 없습니다.
    
- Skype 다음 때문에 Lync Server 2013 회의 정책에서 허용하는 경우에도 1080p 비디오 해상도(인바운드 또는 아웃바운드)를 표시하지 못합니다. 
    
  - Lync Server 2010은 1080p 해상도를 지원하지 않습니다.
    
  - Skype 룸 시스템은 항상 비디오 해상도에 대한 이끌이의 회의 정책에 의해 제한됩니다. 따라서 Lync 2010 풀에서 720p 해상도를 지원하는 경우에도 이끌이의 정책이 720p 해상도를 지원하지 않는 한 Skype 룸 시스템에서 720p 해상도를 활용할 수 없습니다. 
    
- Lync 2013 클라이언트는 회의실에서 LRS 현재 상태 확인을 하여 실제 회의실에서 에코를 방지하기 위해 자동으로 음소거합니다. 이 기능은 Lync Server 2010에서 호스팅되는 모임에서는 작동하지 않습니다.
    
- Lync Server 2010에서 호스팅되는 모임의 데스크톱 공유 성능에는 제한이 있습니다.
    
- 사용자는 회의실 시스템과 함께 Lync 2010에서 호스팅되는 비공개(제한된) 모임에 Skype 없습니다.
    

