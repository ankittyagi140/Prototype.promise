# Prototype.promise

class Mypromise {

  constructor(executor) {
    this.resolveData = null;
    this.isResolved = false;
    this.thenFunc;
    
    const resolve = (value) => {
      this.resolveData = value;
      this.isResolved = true;
      if(typeof this.thenFunc==='function'){
          this.thenFunc(this.resolveData);
      }
    };
    
    executor(resolve);
  }
  
  thenFn() {
    this.thenFunc=fn;
    this.isResolved && this.thenFunc(this.resolveData);
  }
  
}
const promise = new Mypromise((res) => {
  res(2)
}).then(()=>console.log(value))
