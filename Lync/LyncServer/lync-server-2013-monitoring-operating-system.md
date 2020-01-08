---
title: 'Lync Server 2013: 운영 체제 모니터링'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2f8124afcf2d1acbde3518ff625d528d6e34a3e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a><span data-ttu-id="d821f-102">Lync Server 2013의 운영 체제 모니터링</span><span class="sxs-lookup"><span data-stu-id="d821f-102">Monitoring operating system in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d821f-103">_**마지막으로 수정한 주제:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="d821f-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="d821f-104">Lync Server 2013의 모든 서버 및 구성 요소의 성능을 모니터링 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d821f-104">You must monitor the performance of all servers and components in the Lync Server 2013.</span></span> <span data-ttu-id="d821f-105">가장 중요한 구성 요소 중 하나는 운영 체제 자체입니다.</span><span class="sxs-lookup"><span data-stu-id="d821f-105">Obviously, one of the most important components is the operating system itself.</span></span> <span data-ttu-id="d821f-106">Lync 서버 2013는 다음의 x64 버전을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d821f-106">Lync Server 2013 supports x64 editions of:</span></span>

  - <span data-ttu-id="d821f-107">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d821f-107">Windows Server 2008 R2</span></span>

  - <span data-ttu-id="d821f-108">Windows Server 2012 및 Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d821f-108">Windows Server 2012 and Windows Server 2012 R2</span></span>

<span data-ttu-id="d821f-109">운영 체제를 모니터링 하는 가장 투명 한 방법은 Windows Server 운영 체제 관리 팩을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d821f-109">The most transparent way to monitor an operating system is by using Windows Server Operating System Management Pack.</span></span> <span data-ttu-id="d821f-110">Windows Server 2012, Windows Server 2012 R2 및 Windows Server 2008 R2를 실행 하는 컴퓨터의 성능, 상태, 가용성 등의 기본 모니터링 기본 사항을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d821f-110">It provides the fundamental monitoring basics, such as performance, health, and availability for computers that are running Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span>

<span data-ttu-id="d821f-111">이러한 관리 팩은 중요 한 이벤트 및 성능 표시기에 대 한 검색, 경고 및 자동 응답을 통해 문제 해결 시간을 줄이고 Windows Server를 실행 하는 시스템의 전반적인 사용 가능성 및 성능을 높입니다. 운영 체제</span><span class="sxs-lookup"><span data-stu-id="d821f-111">By detecting, alerting, and automatically responding to important events and performance indicators, these management packs reduce resolution times for issues and increase the overall availability and performance of systems that are running the Windows Server operating systems.</span></span>

<span data-ttu-id="d821f-112">System Center Operations Manager 용 관련 Windows Server 관리 팩 외에 다음 시스템 도구 및 리소스를 사용 하 여 운영 체제의 상태를 모니터링할 수 있습니다 (운영 체제 버전에 따라 다름).</span><span class="sxs-lookup"><span data-stu-id="d821f-112">Apart from relevant Windows Server management packs for System Center Operations Manager, the following system tools and resources can be used to monitor the health of the operating system (depending on the operating system version).</span></span>

<div>

## <a name="windows-server2008r2"></a><span data-ttu-id="d821f-113">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d821f-113">Windows Server 2008 R2</span></span>

<span data-ttu-id="d821f-114">Windows Server 2008 R2에는 관리자가 기본 운영 체제 모니터링 및 관리에 도움이 되는 다음과 같은 추가 기능 및 도구가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d821f-114">Windows Server 2008 R2 includes the following additional features and tools to help administrators with basic operating system monitoring and management:</span></span>

  - <span data-ttu-id="d821f-p103">**Windows 리소스 모니터**는 프로세스 및 서비스에서 시스템 리소스가 어떻게 사용되는지를 파악할 수 있게 해주는 강력한 도구입니다. 리소스 모니터를 사용하면 리소스 사용량을 실시간으로 모니터링할 수 있을 뿐 아니라, 응답하지 않는 프로세스를 분석하고, 파일을 사용 중인 응용 프로그램을 식별하고, 프로세스 및 서비스를 제어하는 데에도 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d821f-p103">**Windows Resource Monitor** is a powerful tool for understanding how system resources are used by processes and services. In addition to monitoring resource usage in real time, a Resource Monitor can help analyze unresponsive processes, identify which applications are using files, and control processes and services.</span></span>

  - <span data-ttu-id="d821f-p104">**RAC(Reliability Analysis Component)** 는 시스템 사용 및 안정성에 대한 세부적인 환경 정보를 제공하는 기본 에이전트입니다. 이 정보는 Portable Readers Systems에서 사용할 수 있도록 WMI 인터페이스를 통해 노출됩니다. WMI 인터페이스를 통해 RAC(Reliability Analysis Component)를 노출함으로써 개발자는 응용 프로그램을 모니터링 및 분석하고 안정성과 성능을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d821f-p104">**Reliability Analysis Component** is an in-box agent that provides detailed experience information on system usage and reliability. This information is exposed through a WMI interface to make it available for consumption by Portable Readers Systems. By exposing Reliability Analysis Component through a WMI interface, developers can monitor and analyze applications, increasing reliability and performance.</span></span>

  - <span data-ttu-id="d821f-120">**Windows Server 2008 R2** 는 기본 제공 안정성 분석 구성 요소를 사용 하 여 전체 시스템 사용량 및 시간에 따른 안정성에 대 한 정보를 제공 하는 안정성 인덱스를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="d821f-120">**Windows Server 2008 R2** uses the built-in Reliability Analysis Component to calculate a reliability index, which provides information about overall system usage and stability over time.</span></span> <span data-ttu-id="d821f-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span><span class="sxs-lookup"><span data-stu-id="d821f-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span></span>

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a><span data-ttu-id="d821f-122">Windows Server 2008 Windows 안정성 및 성능 모니터</span><span class="sxs-lookup"><span data-stu-id="d821f-122">Windows Server 2008 Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="d821f-p106">Windows 안정성 및 성능 모니터는 성능 로그 및 경고, 서버 성능 관리자, 시스템 모니터를 포함한 이전 독립 실행형 도구의 기능을 결합하는 MMC 스냅인입니다. 여기에는 성능 데이터 수집 및 이벤트 추적 세션을 사용자 지정하기 위한 그래픽 인터페이스가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d821f-p106">Windows Reliability and Performance Monitor is an MMC Snap-in that combines the functionality of previous stand-alone tools including Performance Logs and Alerts, Server Performance Advisor, and System Monitor. It provides a graphical interface for customizing performance data collection and Event Trace Sessions.</span></span>

<span data-ttu-id="d821f-125">또한 시스템에 대한 변경 사항을 추적하여 시스템 안정성의 변경 사항과 비교하고 이들의 관계를 그래픽으로 나타내는 MMC 스냅인인 안정성 모니터도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d821f-125">It also includes Reliability Monitor, an MMC Snap-in that tracks changes to the system and compares them to changes in system stability, and it provides a graphical view of their relationship.</span></span>

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a><span data-ttu-id="d821f-126">Windows 안정성 및 성능 모니터</span><span class="sxs-lookup"><span data-stu-id="d821f-126">Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="d821f-127">Windows 안정성 및 성능 모니터는 성능 로그, 알림, 시스템 모니터 및 서버 성능 관리자와 같은 이전의 독립 실행형 도구에 대 한 기능을 결합 하는 반면, Windows Server 2008의 몇 가지 새로운 기능을 제공 하 고 있습니다. 다음과 같은 Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d821f-127">While Windows Reliability and Performance Monitor combine functionalities of some former stand-alone tools such as Performance Logs and Alerts, and System Monitor and Server Performance Advisor, it also provides some new functionality to Windows Server 2008 and Windows Server 2008 R2, such as the following:</span></span>

  - <span data-ttu-id="d821f-128">데이터 수집기 집합</span><span class="sxs-lookup"><span data-stu-id="d821f-128">Data Collector Sets</span></span>

  - <span data-ttu-id="d821f-129">자원 보기</span><span class="sxs-lookup"><span data-stu-id="d821f-129">Resource View</span></span>

  - <span data-ttu-id="d821f-130">안정성 모니터</span><span class="sxs-lookup"><span data-stu-id="d821f-130">Reliability Monitor</span></span>

  - <span data-ttu-id="d821f-131">로그를 만들기 위한 마법사 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="d821f-131">Wizards and templates for creating logs</span></span>

<span data-ttu-id="d821f-p107">**데이터 수집기 집합**은 데이터 수집기를 다양한 성능 모니터링 시나리오에 사용하기 위해 재사용 가능 요소로 그룹화합니다. 데이터 수집기 그룹을 데이터 수집기 집합으로 저장한 후에는 단일 속성 변경을 통해 예약과 같은 작업을 전체 집합에 적용할 수 있습니다. Windows 안정성 및 성능 모니터에는 시스템 관리자가 서버 역할 또는 모니터링 시나리오에 관련된 성능 데이터 수집을 즉시 시작하는 데 도움이 되는 기본 데이터 수집기 집합 템플릿이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d821f-p107">**Data Collector Set** groups data collectors into reusable elements for use with different performance monitoring scenarios. After a group of data collectors are stored as a Data Collector Set, operations such as scheduling can be applied to the whole set through a single property change.Windows Reliability and Performance Monitor includes default Data Collector Set templates to help system administrators begin immediately collecting performance data that is specific to a server role or monitoring scenario.</span></span>

<span data-ttu-id="d821f-p108">Windows 안정성 및 성능 모니터 홈페이지는 새 **자원 보기** 화면으로, CPU, 디스크, 네트워크, 메모리 사용의 실시간 그래픽 개요를 제공합니다. 시스템 관리자는 모니터링되는 이러한 각 요소를 확장하여 어느 프로세스에 어느 리소스가 사용되고 있는지를 식별할 수 있습니다. 이전 버전의 Windows에서는 이 실시간 프로세스별 데이터를 작업 관리자에서 제한된 형태로만 확인할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="d821f-p108">The home page of Windows Reliability and Performance Monitor is the new **Resource View** screen, which provides a real-time graphical overview of CPU, disk, network, and memory usage. By expanding each of these monitored elements, system administrators can identify which processes are using which resources. In earlier versions of Windows, this real-time, process-specific data was available only in limited form in Task Manager.</span></span>

<span data-ttu-id="d821f-p109">**안정성 모니터**는 예기치 않은 문제로 인해 시스템의 안정성이 저하되었는지를 나타내는 시스템 안정성 인덱스를 계산합니다. 시간대별 안정성 인덱스 그래프를 통해 문제가 발생하기 시작한 날짜를 빠르게 식별할 수 있습니다. 관련된 시스템 안정성 보고서에는 안정성 저하의 원인을 해결하는 데 도움이 되는 세부 정보가 제공됩니다. 시스템에 대한 변경 사항(응용 프로그램 설치 또는 제거, 운영 체제 업데이트 또는 드라이버 추가/수정)과 오류(응용 프로그램 오류, 운영 체제 작동 중지 또는 하드웨어 오류)를 나란히 표시하여 살펴보면 문제 해결 방안을 빠르게 마련할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d821f-p109">**Reliability Monitor** calculates a System Stability Index that reflects whether unexpected issues reduced the reliability of the system. A graph of the Stability Index over time quickly identifies dates when issues began to occur. The accompanying System Stability Report provides details to help troubleshoot the cause of reduced reliability. By viewing changes to the system (installation or removal of applications, updates to the operating system, or addition or modification of drivers) side by side with failures (application failures, operating system crashes, or hardware failures), a strategy for addressing the issues can be developed quickly.</span></span>

<span data-ttu-id="d821f-p110">로그 파일에 카운터를 추가하고 해당 시작, 중지, 기간을 예약하는 작업을 이제 **마법사 인터페이스**에서 수행할 수 있습니다. 또한 이 구성을 템플릿으로 저장하면 시스템 관리자가 다른 컴퓨터에서 데이터 수집기 선택 및 예약 프로세스를 반복하지 않고 동일한 로그를 수집할 수 있습니다. 성능 로그 및 경고 기능은 모든 데이터 수집기 집합에 사용할 수 있도록 Windows 안정성 및 성능 모니터에 통합되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d821f-p110">Adding counters to log files and scheduling their start, stop, and duration can now be performed through a **Wizard interface**. In addition, saving this configuration as a template enables system administrators to collect the same log on other computers without repeating the data collector selection and scheduling processes. Performance Logs and Alerts features were incorporated into the Windows Reliability and Performance Monitor for use with any Data Collector Set.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

