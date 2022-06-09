# React Stepper Wizard

A simple higly customizable Wizard component for displaying pages in react app.

##### Based on the React hooks and reactive programing.
#### No extra dependencies pure react js code & lightweight.

## Features
1. Easly handel user cases for wizard.
2. Provide highly customization to fit in all major User cases.
3. Super Easy to use.
4. Open source Free to use.

## Installation
```sh
npm install @surinderlohat/react-stepper-wizard
or
yarn add @surinderlohat/react-stepper-wizard
```

## How to use
```sh
import { StepperWizard } from '@surinderlohat/react-stepper-wizard';
import { FC } from 'react';

const BasicExample: FC = () => {
  return (
    <div style={{ width: 350 }}>
      <StepperWizard
        onStepChange={activeStep => {
          console.log('onStepChange', activeStep);
        }}
      >
        <div>Step 1</div>
        <div>Step 2</div>
        <div>Step 3</div>
        <div>Step 4</div>
        <div>Step 5</div>
        <div>Step 6</div>
      </StepperWizard>
    </div>
  );
};

export default BasicExample;

```
## API Documentation

```
{
  children?: ReactChild;
  
  /* starting step of wizard */
  defaultStep?: number;
  
  /* current active step*/
  activeStep?: number;
  
  /**Place action buttons on bottom or top or pass hidden if want to use your own actions*/
  actionsPlacement?: 'bottom' | 'top' | 'hidden';
  
  /**used to access StepperWizard hook in parent component case if wants to control using the parent component
   * i.e const hookRef = useRef();
   * <div>
   * <StepperWizard hookRef={hookRef}>
   * <Step1/>
   * <Step2/>
   * </StepperWizard>
   * <button onClick={()=>hookRef.current?.goToSpecificStep(2)}>
   *  Got Step 2
   * </button>
   * </div>
   */
  hookRef?: Ref<IUseStepperWizard>;
  
  /**Return current active step */
  onStepChange?: (activeStep: number) => void;
  
  /**
   * Render custom action buttons i.e if your application need some custom action button UI
   * param : state useStepperWizard hook state to control navigation
   * props : props provided by the component in which we are using it
   */
  renderCustomActions?: (state: any, props: any) => ReactNode;
  
  /**Name of the back button*/
  previousButtonName?: string;
  
  /**Name of next button*/
  nextButtonName?: string;
  
  /**Perform custom control for previous button click*/
  onPreviousButtonClick?: Function;
  
  /**Perform custom control for next button click*/
  onNextButtonClick?: Function;
  
  /**Change color of the action buttons*/
  actionButtonsColor?: string;
  
  /**Pass classes to child's for UI customization*/
  classes?: {
    rootDiv?: string;
    actionButtonContainer?: string;
    prevActionButton?: string;
    nextActionButton?: string;
  };
  
  /**Pass styles to child's for UI customization*/
  styles?: {
    rootDiv?: React.CSSProperties;
    actionButtonContainer?: React.CSSProperties;
    prevActionButton?: React.CSSProperties;
    nextActionButton?: React.CSSProperties;
  };
};
```

## License
MIT **Free Software!**
