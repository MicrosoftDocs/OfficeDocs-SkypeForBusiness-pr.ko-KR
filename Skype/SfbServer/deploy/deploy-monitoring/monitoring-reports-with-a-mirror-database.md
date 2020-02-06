---
title: 비즈니스용 Skype 서버에서 모니터링 보고서와 미러 데이터베이스 연결
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: '요약: 비즈니스용 Skype 서버에서 사용 하는 미러 데이터베이스와 모니터링 보고서를 연결 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 77e852860239ae6f87fce2b49fb6fa9f9d7c0834
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41789936"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 모니터링 보고서와 미러 데이터베이스 연결 
 
**요약:** 비즈니스용 Skype 서버에서 사용 하는 미러 데이터베이스와 모니터링 보고서를 연결 하는 방법에 대해 알아봅니다.
  
## <a name="monitor-reports-with-a-mirror-database"></a>미러 데이터베이스로 보고서 모니터링

모니터링 데이터베이스에 대 한 미러를 구성 하는 경우 장애 조치 (failover)가 발생할 경우 미러 데이터베이스가 기본 데이터베이스로 이동 합니다. 그러나 비즈니스용 Skype 서버 모니터링 보고서를 사용 하는 경우 장애 조치가 발생 하는 경우 모니터링 보고서가 미러 데이터베이스에 연결 되지 않는 것을 확인할 수 있습니다. 모니터링 보고서를 설치 하는 경우 기본 데이터베이스의 위치만 지정 하기 때문입니다. 미러 데이터베이스의 위치를 지정 하지 않습니다.
  
모니터링 보고서에서 미러 데이터베이스로 자동으로 장애 조치 (failover)를 받으려면 모니터링 보고서에 사용 되는 두 데이터베이스 (통화 정보 레코드 데이터에 대 한 데이터베이스 및 다른 품질의 경우)에 따라 미러 데이터베이스를 "장애 조치 (failover) 파트너"로 추가 해야 합니다. 체감 품질 (환경) 데이터). 모니터링 보고서를 설치한 후에는이 단계를 수행 해야 합니다. 이러한 두 데이터베이스에서 사용 하는 연결 문자열 값을 수동으로 편집 하 여 장애 조치 파트너 정보를 추가할 수 있습니다. 이렇게 하려면 다음 절차를 수행 합니다.
  
1. Internet Explorer를 사용 하 여 **SQL Server Reporting Services** 홈 페이지를 엽니다. Reporting Services 홈 페이지 URL에는 다음이 포함 됩니다.
    
   - **Http:** prefix.
    
   - Reporting Services가 설치 된 컴퓨터의 FQDN (정규화 된 도메인 이름) (예: **atl-sql-001.litwareinc.com**)
    
   - 문자열 **/Reports_**.
    
   - 모니터링 보고서가 설치 된 데이터베이스 인스턴스의 이름입니다 (예: **archinst**).
    
     예를 들어, SQL Server Reporting Services가 컴퓨터 atl-sql-001.litwareinc.com에 설치 되어 있고 모니터링 보고서가 데이터베이스 인스턴스 archinst를 사용 하는 경우 홈페이지 URL은 다음과 같이 표시 됩니다.
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. Reporting Services 홈 페이지에 액세스 한 후에는 **Serverreports**를 클릭 한 다음 **Reports_Content**를 클릭 합니다. 그러면 비즈니스용 Skype 서버 모니터링 보고서의 **Reports_Content** 페이지로 이동 합니다.
    
3. **Reports_Content** 페이지에서 **cdrdb** 데이터 원본을 클릭 합니다.
    
4. **Cdrdb** 페이지의 **속성** 탭에서 **연결 문자열**이라는 레이블이 붙은 텍스트 상자를 찾습니다. 현재 연결 문자열은 다음과 유사 하 게 표시 됩니다.
    
    데이터 원본 = (로컬) \archinst, 초기 카탈로그 = LcsCDR
    
5. 연결 문자열을 편집 하 여 미러 데이터베이스의 서버 이름과 데이터베이스 인스턴스를 포함 합니다. 예를 들어, 서버의 이름이 atl-001이 고 미러 데이터베이스가 archinst 인스턴스에 있으면이 구문을 사용 하 여 미러 데이터베이스를 지정 하기 위해 추가 해야 합니다.
    
    장애 조치 파트너 = atl-mirror-001\archinst
    
    편집한 연결 문자열은 다음과 같이 표시 됩니다.
    
    데이터 원본 = (로컬) \archinst 장애 조치 (Failover) 파트너 = atl-mirror-001\archinst; 초기 카탈로그 = LcsCDR
    
6. 연결 문자열을 업데이트 한 후 **적용**을 클릭 합니다.
    
7. **Cdrdb** 페이지에서 **Reports_Content** 링크를 클릭 합니다. **Qmsdb** 데이터 원본을 클릭 한 다음 체감 품질 데이터베이스에 대 한 연결 문자열을 편집 합니다. 예를 들면 다음과 같습니다.
    
    데이터 원본 = (로컬) \archinst 장애 조치 (Failover) 파트너 = atl-mirror-001\archinst; 초기 카탈로그 = QoEMetrics
    
8. **적용**을 클릭 합니다.
    
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 모니터링 보고서 설치](install-monitoring-reports.md)
  
[비즈니스용 Skype 서버에서 모니터링 보고서 사용](../../manage/health-and-monitoring/monitoring-reports.md)
