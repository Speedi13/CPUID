# CPUID
Information that is available in this struct is
- General information
  - HighestFunctionParameter
  - HighestExtendedFunctionParameter
  - ManufacturerID
  - ProcessorNameStringIdentifier
* Processor Version Information
  - SteppingID
  - Model
  - FamilyID
  - ProcessorType
  - ExtendedModelID
  - ExtendedFamilyID
* Additional Information
  - BrandIndex
  - CLFLUSH
  - LogicalProcessorCount ( AMD only )
  - LocalApicId
* Feature Information
  - [all Feature Information bits of EDX and ECX](https://en.wikipedia.org/w/index.php?title=CPUID#EAX=1:_Processor_Info_and_Feature_Bits)
* Feature Extended Information
  - [all Extended Feature Information bits of EBX, ECX and EDX](https://en.wikipedia.org/w/index.php?title=CPUID#EAX=7,_ECX=0:_Extended_Features)
* AMD Feature Extended Information
  - [all AMD flags in ECX, EDX](https://en.wikipedia.org/w/index.php?title=CPUID#EAX=80000001h:_Extended_Processor_Info_and_Feature_Bits)
# Code usage
```cpp
CpuInfo Information = CpuInfo();
printf("ManufacturerID: [%s]\n",                     Information.ManufacturerID);
printf("ProcessorNameStringIdentifier: [%s]\n",      Information.ProcessorNameStringIdentifier);
printf("      Conditional Moves supported:    %u\n", Information.FeatureInformation.CMOV );
printf("[AMD] Conditional Moves supported:    %u\n", Information.AMDFeatureExtendedInformation.CMOV );
printf("      AES instruction set supported:  %u\n", Information.FeatureInformation.AES );
printf("      Intel SHA extensions supported: %u\n", Information.FeatureExtendedInformation.SHA );
printf("      On-chip RNG supported:          %u\n", Information.FeatureInformation.RDRND );
```
