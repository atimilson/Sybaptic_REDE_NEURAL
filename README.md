# Sybaptic_REDE_NEURAL
Teste da biblioteca js para rede neural simples 

https://caza.la/synaptic/#/

var synaptic = require('synaptic');
this.network = new synaptic.Architect.Perceptron(40, 25, 3);


creatures.forEach(function(creature)
{
    // move
    var input = [];
    for (var i in creatures)
    {
      input.push(creatures[i].location.x);
      input.push(creatures[i].location.y);
      input.push(creatures[i].velocity.x);
      input.push(creatures[i].velocity.y);
    }
    var output = creature.network.activate(input);
    creature.moveTo(output);
    
    // learn
    var learningRate = .3;
    var target = [
      targetX(creature), 
      targetY(creature), 
      targetAngle(creature)];
    creature.network.propagate(learningRate, target);
});
