---
title: CorDebugRegister Numaralandırması
ms.date: 03/30/2017
api_name:
- CorDebugRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugRegister
helpviewer_keywords:
- CorDebugRegister enumeration [.NET Framework debugging]
ms.assetid: 003bb138-7960-4291-ac88-0d87e470ff70
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bed3c461935c5a2bc912ed9ed16d147fddaf8a1a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739660"
---
# <a name="cordebugregister-enumeration"></a><span data-ttu-id="988c4-102">CorDebugRegister Numaralandırması</span><span class="sxs-lookup"><span data-stu-id="988c4-102">CorDebugRegister Enumeration</span></span>
<span data-ttu-id="988c4-103">Bir verilen işlemci mimarisi ile ilişkili olan kayıtları belirtir.</span><span class="sxs-lookup"><span data-stu-id="988c4-103">Specifies the registers associated with a given processor architecture.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="988c4-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="988c4-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugRegister {  
  
    REGISTER_INSTRUCTION_POINTER = 0,  
    REGISTER_STACK_POINTER,  
    REGISTER_FRAME_POINTER,  
  
    REGISTER_X86_EIP = 0,  
    REGISTER_X86_ESP,  
    REGISTER_X86_EBP,  
  
    REGISTER_X86_EAX,  
    REGISTER_X86_ECX,  
    REGISTER_X86_EDX,  
    REGISTER_X86_EBX,  
  
    REGISTER_X86_ESI,  
    REGISTER_X86_EDI,  
  
    REGISTER_X86_FPSTACK_0,  
    REGISTER_X86_FPSTACK_1,  
    REGISTER_X86_FPSTACK_2,  
    REGISTER_X86_FPSTACK_3,  
    REGISTER_X86_FPSTACK_4,  
    REGISTER_X86_FPSTACK_5,  
    REGISTER_X86_FPSTACK_6,  
    REGISTER_X86_FPSTACK_7,  
  
    REGISTER_AMD64_RIP = 0,  
    REGISTER_AMD64_RSP,  
    REGISTER_AMD64_RBP,  
    REGISTER_AMD64_RAX,  
    REGISTER_AMD64_RCX,  
    REGISTER_AMD64_RDX,  
    REGISTER_AMD64_RBX,  
    REGISTER_AMD64_RSI,  
    REGISTER_AMD64_RDI,  
    REGISTER_AMD64_R8,  
    REGISTER_AMD64_R9,  
    REGISTER_AMD64_R10,  
    REGISTER_AMD64_R11,  
    REGISTER_AMD64_R12,  
    REGISTER_AMD64_R13,  
    REGISTER_AMD64_R14,  
    REGISTER_AMD64_R15,  
  
    REGISTER_AMD64_XMM0,  
    REGISTER_AMD64_XMM1,  
    REGISTER_AMD64_XMM2,  
    REGISTER_AMD64_XMM3,  
    REGISTER_AMD64_XMM4,  
    REGISTER_AMD64_XMM5,  
    REGISTER_AMD64_XMM6,  
    REGISTER_AMD64_XMM7,  
    REGISTER_AMD64_XMM8,  
    REGISTER_AMD64_XMM9,  
    REGISTER_AMD64_XMM10,  
    REGISTER_AMD64_XMM11,  
    REGISTER_AMD64_XMM12,  
    REGISTER_AMD64_XMM13,  
    REGISTER_AMD64_XMM14,  
    REGISTER_AMD64_XMM15,  
  
    REGISTER_IA64_BSP = REGISTER_FRAME_POINTER,  
    REGISTER_IA64_R0  = REGISTER_IA64_BSP + 1,  
    REGISTER_IA64_F0  = REGISTER_IA64_R0  + 128,  
    REGISTER_ARM_PC = 0,  
    REGISTER_ARM_SP,  
    REGISTER_ARM_R0,  
    REGISTER_ARM_R1,  
    REGISTER_ARM_R2,  
    REGISTER_ARM_R3,  
    REGISTER_ARM_R4,  
    REGISTER_ARM_R5,  
    REGISTER_ARM_R6,  
    REGISTER_ARM_R7,  
    REGISTER_ARM_R8,  
    REGISTER_ARM_R9,  
    REGISTER_ARM_R10,  
    REGISTER_ARM_R11,  
    REGISTER_ARM_R12,  
    REGISTER_ARM_LR,  
  
} CorDebugRegister;  
```  
  
## <a name="members"></a><span data-ttu-id="988c4-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="988c4-105">Members</span></span>  
  
|<span data-ttu-id="988c4-106">Üye</span><span class="sxs-lookup"><span data-stu-id="988c4-106">Member</span></span>|<span data-ttu-id="988c4-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="988c4-107">Description</span></span>|  
|------------|-----------------|  
|`REGISTER_INSTRUCTION_POINTER`|<span data-ttu-id="988c4-108">Bir yönerge işaretçisini herhangi bir işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-108">An instruction pointer register on any processor.</span></span>|  
|`REGISTER_STACK_POINTER`|<span data-ttu-id="988c4-109">Yığın işaretçisi, herhangi bir işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-109">A stack pointer register on any processor.</span></span>|  
|`REGISTER_FRAME_POINTER`|<span data-ttu-id="988c4-110">Çerçeve işaretçisini herhangi bir işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-110">A frame pointer register on any processor.</span></span>|  
|`REGISTER_X86_EIP`|<span data-ttu-id="988c4-111">Yönerge işaretçisi kaydı x86 işlemci.</span><span class="sxs-lookup"><span data-stu-id="988c4-111">The instruction pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_ESP`|<span data-ttu-id="988c4-112">Yığın işaretçisi kaydı x86 işlemci.</span><span class="sxs-lookup"><span data-stu-id="988c4-112">The stack pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_EBP`|<span data-ttu-id="988c4-113">Taban işaretçisi kaydı x86 işlemci.</span><span class="sxs-lookup"><span data-stu-id="988c4-113">The base pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_EAX`|<span data-ttu-id="988c4-114">Bir veri kaydetme üzerinde x86 işlemci.</span><span class="sxs-lookup"><span data-stu-id="988c4-114">The A data register on the x86 processor.</span></span>|  
|`REGISTER_X86_ECX`|<span data-ttu-id="988c4-115">C veri x86 kaydettirmek işlemci.</span><span class="sxs-lookup"><span data-stu-id="988c4-115">The C data register on the x86 processor.</span></span>|  
|`REGISTER_X86_EDX`|<span data-ttu-id="988c4-116">D verileri üzerinde x86 kaydı işlemci.</span><span class="sxs-lookup"><span data-stu-id="988c4-116">The D data register on the x86 processor.</span></span>|  
|`REGISTER_X86_EBX`|<span data-ttu-id="988c4-117">B veri kaydetme üzerinde x86 işlemci.</span><span class="sxs-lookup"><span data-stu-id="988c4-117">The B data register on the x86 processor.</span></span>|  
|`REGISTER_X86_ESI`|<span data-ttu-id="988c4-118">Kaynak dizin yazmacı x86 işlemci.</span><span class="sxs-lookup"><span data-stu-id="988c4-118">The source index register on the x86 processor.</span></span>|  
|`REGISTER_X86_EDI`|<span data-ttu-id="988c4-119">Hedef dizin yazmacı x86 işlemci.</span><span class="sxs-lookup"><span data-stu-id="988c4-119">The destination index register on the x86 processor.</span></span>|  
|`REGISTER_X86_FPSTACK_0`|<span data-ttu-id="988c4-120">Yığın x86 kayan nokta (dp) kaydı 0 işlemci.</span><span class="sxs-lookup"><span data-stu-id="988c4-120">The stack register 0 on the x86 floating-point (FP) processor.</span></span>|  
|`REGISTER_X86_FPSTACK_1`|<span data-ttu-id="988c4-121">#1 yığın FP işlemci üzerinde x86 kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-121">The #1 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_2`|<span data-ttu-id="988c4-122">#2 yığın FP işlemci üzerinde x86 kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-122">The #2 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_3`|<span data-ttu-id="988c4-123">#3 yığın FP işlemci üzerinde x86 kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-123">The #3 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_4`|<span data-ttu-id="988c4-124">#4 yığın FP işlemci üzerinde x86 kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-124">The #4 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_5`|<span data-ttu-id="988c4-125">#5 yığın FP işlemci üzerinde x86 kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-125">The #5 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_6`|<span data-ttu-id="988c4-126">#6 yığın FP işlemci üzerinde x86 kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-126">The #6 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_7`|<span data-ttu-id="988c4-127">#7 yığın FP işlemci üzerinde x86 kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-127">The #7 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_AMD64_RIP`|<span data-ttu-id="988c4-128">Yönerge işaretçisi AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-128">The instruction pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RSP`|<span data-ttu-id="988c4-129">Yığın işaretçisi AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-129">The stack pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RBP`|<span data-ttu-id="988c4-130">Taban işaretçisi AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-130">The base pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RAX`|<span data-ttu-id="988c4-131">Bir veri AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-131">The A data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RCX`|<span data-ttu-id="988c4-132">C veri AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-132">The C data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RDX`|<span data-ttu-id="988c4-133">D veri AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-133">The D data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RBX`|<span data-ttu-id="988c4-134">B veri AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-134">The B data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RSI`|<span data-ttu-id="988c4-135">Kaynak dizini AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-135">The source index register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RDI`|<span data-ttu-id="988c4-136">Hedef dizin AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-136">The destination index register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R8`|<span data-ttu-id="988c4-137">#8 veri AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-137">The #8 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R9`|<span data-ttu-id="988c4-138">#9 veri AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-138">The #9 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R10`|<span data-ttu-id="988c4-139">#10 veri AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-139">The #10 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R11`|<span data-ttu-id="988c4-140">#11 veri AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-140">The #11 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R12`|<span data-ttu-id="988c4-141">#12 veri AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-141">The #12 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R13`|<span data-ttu-id="988c4-142">#13 veri AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-142">The #13 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R14`|<span data-ttu-id="988c4-143">#14 veri AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-143">The #14 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R15`|<span data-ttu-id="988c4-144">#15 veri AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-144">The #15 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM0`|<span data-ttu-id="988c4-145">Multimedya #0 AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-145">The #0 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM1`|<span data-ttu-id="988c4-146">Multimedya #1 AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-146">The #1 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM2`|<span data-ttu-id="988c4-147">Multimedya #2 AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-147">The #2 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM3`|<span data-ttu-id="988c4-148">Multimedya #3 AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-148">The #3 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM4`|<span data-ttu-id="988c4-149">Multimedya #4 AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-149">The #4 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM5`|<span data-ttu-id="988c4-150">Multimedya #5 AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-150">The #5 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM6`|<span data-ttu-id="988c4-151">Multimedya #6 AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-151">The #6 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM7`|<span data-ttu-id="988c4-152">Multimedya #7 AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-152">The #7 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM8`|<span data-ttu-id="988c4-153">Multimedya #8 AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-153">The #8 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM9`|<span data-ttu-id="988c4-154">Multimedya #9 AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-154">The #9 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM10`|<span data-ttu-id="988c4-155">Multimedya #10 AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-155">The #10 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM11`|<span data-ttu-id="988c4-156">Multimedya #11 AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-156">The #11 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM12`|<span data-ttu-id="988c4-157">Multimedya #12 AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-157">The #12 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM13`|<span data-ttu-id="988c4-158">Multimedya #13 AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-158">The #13 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM14`|<span data-ttu-id="988c4-159">Multimedya #14 AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-159">The #14 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM15`|<span data-ttu-id="988c4-160">Multimedya #15 AMD64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-160">The #15 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_IA64_BSP`|<span data-ttu-id="988c4-161">Yığın işaretçisi IA-64 işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-161">The stack pointer register on the IA-64 processor.</span></span>|  
|`REGISTER_IA64_R0`|<span data-ttu-id="988c4-162">#0 veri IA-64 işlemci kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-162">The #0 data register on the IA-64 processor.</span></span>|  
|`REGISTER_IA64_F0`|<span data-ttu-id="988c4-163">#0 FP veri IA-64 işlemci kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-163">The #0 FP data register on the IA-64 processor.</span></span>|  
|`REGISTER_ARM_PC`|<span data-ttu-id="988c4-164">Program sayacının ARM işlemci üzerinde (R15 kayıtları) kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-164">The program counter register (R15) on the ARM processor.</span></span>|  
|`REGISTER_ARM_SP`|<span data-ttu-id="988c4-165">Yığın işaretçisi, ARM işlemci üzerinde (R13) kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-165">The stack pointer register (R13) on the ARM processor.</span></span>|  
|`REGISTER_ARM_R0`|<span data-ttu-id="988c4-166">Veri R0 ARM işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-166">Data register R0 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R1`|<span data-ttu-id="988c4-167">Veri R1 ARM işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-167">Data register R1 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R2`|<span data-ttu-id="988c4-168">Veri R2 ARM işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-168">Data register R2 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R3`|<span data-ttu-id="988c4-169">Veri R3 ARM işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-169">Data register R3 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R4`|<span data-ttu-id="988c4-170">ARM işlemci üzerinde R4 kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-170">Register R4 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R5`|<span data-ttu-id="988c4-171">ARM işlemci üzerinde R5 kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-171">Register R5 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R6`|<span data-ttu-id="988c4-172">ARM işlemci üzerinde r6 kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-172">Register R6 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R7`|<span data-ttu-id="988c4-173">R7 kaydetme (Flash çerçeve işaretçisi) ARM işlemci üzerinde.</span><span class="sxs-lookup"><span data-stu-id="988c4-173">Register R7 (the THUMB frame pointer) on the ARM processor.</span></span>|  
|`REGISTER_ARM_R8`|<span data-ttu-id="988c4-174">R8, ARM işlemci üzerinde kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-174">Register R8 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R9`|<span data-ttu-id="988c4-175">ARM işlemci üzerinde R9 kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-175">Register R9 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R10`|<span data-ttu-id="988c4-176">ARM işlemci üzerinde R10 kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-176">Register R10 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R11`|<span data-ttu-id="988c4-177">ARM işlemci çerçeve işaretçisi.</span><span class="sxs-lookup"><span data-stu-id="988c4-177">The frame pointer on the ARM processor.</span></span>|  
|`REGISTER_ARM_R12`|<span data-ttu-id="988c4-178">ARM işlemci üzerinde R12 kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-178">Register R12 on the ARM processor.</span></span>|  
|`REGISTER_ARM_LR`|<span data-ttu-id="988c4-179">Bağlantı, ARM işlemci üzerinde (R14) kaydedin.</span><span class="sxs-lookup"><span data-stu-id="988c4-179">The link register (R14) on the ARM processor.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="988c4-180">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="988c4-180">Remarks</span></span>  
 <span data-ttu-id="988c4-181">128 genel amaçlı veri kayıtları ve 128 kayan nokta veri kayıtları IA-64 işlemci, ancak yalnızca değerleri `REGISTER_IA64_R0` ve `REGISTER_IA64_F0` sağlanır.</span><span class="sxs-lookup"><span data-stu-id="988c4-181">There are 128 general-purpose data registers and 128 floating-point data registers on the IA-64 processor, but only values `REGISTER_IA64_R0` and `REGISTER_IA64_F0` are provided.</span></span> <span data-ttu-id="988c4-182">Diğer değerleri aşağıdaki gibi belirlenir:</span><span class="sxs-lookup"><span data-stu-id="988c4-182">The other values can be determined as follows:</span></span>  
  
- <span data-ttu-id="988c4-183">Kayıt numarası eklemek `REGISTER_IA64_R0` değerleri `REGISTER_IA64_R1` aracılığıyla `REGISTER_IA64_R127`, karşılık IA-64 işlemci #127 verilerini kasayla aracılığıyla #1 veri kaydı.</span><span class="sxs-lookup"><span data-stu-id="988c4-183">Add the register number to `REGISTER_IA64_R0` for values `REGISTER_IA64_R1` through `REGISTER_IA64_R127`, which correspond to the #1 data register through the #127 data register on the IA-64 processor.</span></span>  
  
- <span data-ttu-id="988c4-184">Kayıt numarası eklemek `REGISTER_IA64_F0` değerleri `REGISTER_IA64_F1` aracılığıyla `REGISTER_IA64_F127`, hangi karşılık #1 FP veri register-#127 IA-64 işlemci FP veri kaydı.</span><span class="sxs-lookup"><span data-stu-id="988c4-184">Add the register number to `REGISTER_IA64_F0` for values `REGISTER_IA64_F1` through `REGISTER_IA64_F127`, which correspond to the #1 FP data register through the #127 FP data register on the IA-64 processor.</span></span>  
  
 <span data-ttu-id="988c4-185">Örneğin, #83 veri kaydı IA-64 işlemci üzerinde belirtmeniz gerekiyorsa, kullanın `REGISTER_IA64_R0` + 83.</span><span class="sxs-lookup"><span data-stu-id="988c4-185">For example, if you need to specify the #83 data register on the IA-64 processor, use `REGISTER_IA64_R0` + 83.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="988c4-186">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="988c4-186">Requirements</span></span>  
 <span data-ttu-id="988c4-187">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="988c4-187">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="988c4-188">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="988c4-188">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="988c4-189">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="988c4-189">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="988c4-190">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="988c4-190">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="988c4-191">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="988c4-191">See also</span></span>

- [<span data-ttu-id="988c4-192">Hata Ayıklama Sabit Listeleri</span><span class="sxs-lookup"><span data-stu-id="988c4-192">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
